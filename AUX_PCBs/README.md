# Custom assembly using Kikit JLC

Due to JLCPCB's new assembly policy, soldering on the bottom side or using a non-black PCB will incur additional charges.
Bottom side soldering is not possible if the "Economic" assembly option is selected.
As the bottom side soldering is only for the connector, manual assembly is recommended.  
But.. if you ordering more than 31 boards, it is more economical to choose the `Standard assembly` option with panelization.  
If you have any further questions, please feel free to contact me!(Issues, mail, Discord, etc.)  

- You need `KiCad 6.0 Command Prompt` and [Kikit](https://github.com/yaqwsx/KiKit) with KiCad 6

## Panalize and Fabrication

```batch
kikit panelize ^
    -p :jlcTooling ^
    --layout "grid; rows: 7; cols: 3; space: 3mm" ^
    --tabs "fixed; hwidth: 10mm; vwidth: 15mm" ^
    --cuts vcuts ^
    --source "tolerance: 1000mm" ^
    --framing "tightframe; width: 5mm; space: 3mm; " ^
    --post "millradius: 1mm" ^
    "./FineMotion_AUX.kicad_pcb" ^
    "FineMotion_AUX_panel.kicad_pcb"

kikit fab jlcpcb ^
    --assembly ^
    --schematic ./FineMotion_AUX.kicad_sch ^
    --ignore TP1,J1 ^
    "./FineMotion_AUX_panel.kicad_pcb" ^
    "./Gerber/FineMotion_Panel"

```

## Fabrication Only

### Using Default Configuration

```batch
kikit fab jlcpcb ^
    --assembly ^
    --schematic ./FineMotion_AUX.kicad_sch ^
    --ignore TP1,TP2 ^
    --no-drc ^
    "./FineMotion_AUX_panel.kicad_pcb" ^
    "./Gerber/FineMotion"
```

<br><hr><br>

## Panalize and Fabrication Extension Sensor

```batch
```

## Fabrication Extension Sensor Only

### Using Default Configuration

```batch
```
