# Custom assembly using Kikit JLC

Due to JLCPCB's new assembly policy, soldering on the bottom side or using a non-black PCB will incur additional charges.   
Bottom side soldering is not possible if the "Economic" assembly option is selected.   
As the bottom side soldering is only for the connector, manual assembly is recommended.   

You need `KiCad 6.0 Command Prompt` and [Kikit](https://github.com/yaqwsx/KiKit) with KiCad 6

## Panalize and Fabrication
```batch
kikit panelize ^
    -p :jlcTooling ^
    --layout "grid; rows: 7; cols: 3; space: 3mm" ^
    --tabs "fixed; hwidth: 10mm; vwidth: 15mm" ^
    --cuts vcuts ^
    --source "tolerance: 1000mm" ^
    --post "millradius: 1mm" ^
    "./FineMotion-5.kicad_pcb" ^
    "FineMotion-5_panel.kicad_pcb"

kikit fab jlcpcb ^
    --assembly ^
    --schematic ./FineMotion-5.kicad_sch ^
    --ignore TP1,TP2 ^
    --no-drc ^
    "./FineMotion-5_panel.kicad_pcb" ^
    "./Gerber/FineMotion_Panel"
```

## Fabrication Only

### Using Default Configuration
```batch
kikit fab jlcpcb ^
    --assembly ^
    --schematic ./FineMotion-5.kicad_sch ^
    --ignore TP1,TP2 ^
    --no-drc ^
    "./FineMotion-5_panel.kicad_pcb" ^
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
<!--
### Using internal MPU-6050+QMC5883L and Left side Lipo
```batch
kikit fab jlcpcb ^
    --assembly ^
    --schematic ./KTracker.kicad_sch ^
    --ignore BT1,J1,J4,J5 ^
    --no-drc ./KTracker.kicad_pcb ^
    "./Gerber/Using internal MPU-6050+QMC5883L and Left side Lipo"
```

### Using GY-521 and bottom Lipo
```batch
kikit fab jlcpcb ^
    --assembly ^
    --schematic ./KTracker.kicad_sch ^
    --ignore U8,U3,R20,R21,C16,C12,C11,R12,R11,BT1,J3,J4,J5 ^
    --no-drc ./KTracker.kicad_pcb ^
    "./Gerber/Using GY-521 and bottom Lipo"

```

### Using GY-521 and 18650
```batch
kikit fab jlcpcb ^
    --assembly ^
    --schematic ./KTracker.kicad_sch ^
    --ignore U8,U3,R20,R21,C16,C12,C11,R12,R11,J1,J3,J4,J5 ^
    --no-drc ./KTracker.kicad_pcb ^
    "./Gerber/Using GY-521 and 18650"

```

kikit fab jlcpcb --assembly --schematic ./FineMotion-5.kicad_sch --ignore TP1,TP2 --no-drc ./FineMotion-5.kicad_pcb "./Gerber/FM6500"

kikit fab jlcpcb --assembly --schematic ./KTracker_AUX.kicad_sch  --ignore A1 --no-drc ./KTracker_AUX.kicad_pcb "./Gerber/FM6500E"


kikit panelize ^
    -p :jlcTooling ^
    --layout "grid; rows: 7; cols: 3; space: 3mm" ^
    --tabs "fixed; hwidth: 10mm; vwidth: 15mm" ^
    --cuts vcuts ^
    --source "tolerance: 1000mm" ^
    --post "millradius: 1mm" ^
    "./FineMotion-5.kicad_pcb" ^
    "FineMotion-5_panel.kicad_pcb"

kikit fab jlcpcb ^
    --assembly ^
    --schematic ./FineMotion-5.kicad_sch ^
    --ignore TP1,TP2 ^
    --no-drc ^
    "./FineMotion-5_panel.kicad_pcb" ^
    "./Gerber/FineMotion_Panel"

---

-->


