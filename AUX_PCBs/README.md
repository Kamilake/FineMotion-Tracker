# Custom assembly using Kikit JLC

Due to JLCPCB's new assembly policy, soldering on the bottom side or using a non-black PCB will incur additional charges.   
Bottom side soldering is not possible if the "Economic" assembly option is selected.   
   
   
As the bottom side soldering is only for the connector, manual assembly is recommended.   

## Panalize and Fab
```batch
kikit panelize ^
    -p :jlcTooling ^
    --layout "grid; rows: 5; cols: 10;" ^
    --source "tolerance: 1000mm" ^
    --tabs full ^
    --cuts vcuts ./KTracker.kicad_pcb ^
    KTracker_panel.kicad_pcb

kikit fab jlcpcb ^
    --assembly ^
    --schematic ./KTracker.kicad_sch ^
    --ignore J1 ^
    --no-drc ./KTracker_panel.kicad_pcb ^
    ./fab
```

## Only Fab

### Using internal MPU-6050+QMC5883L and bottom Lipo
```batch
kikit fab jlcpcb ^
    --assembly ^
    --schematic ./KTracker.kicad_sch ^
    --ignore BT1,J3,J4,J5 ^
    --no-drc ./KTracker.kicad_pcb ^
    "./Gerber/Using internal MPU-6050+QMC5883L and bottom Lipo"
```
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
