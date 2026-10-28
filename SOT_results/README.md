# SOT angular-dependence results

This directory contains the decoded and analyzed files from the uploaded `2402数据处理.rar` archive for the L10-MnGa/Pt/Co zero-field SOT switching study.

## Data provenance

### Measured data

These files are decoded from Origin OPJU projects that were present in the uploaded archive:

- `extracted_measured_branches.csv`
- `measured_branches.csv`
- `measured_angle_amplitudes.csv`
- `measured_scan_amplitudes.csv`
- `measured_curves_by_angle.png`
- `实测回线_按角度.png`

Measured angles present in the archive: 0°, 45°, 75°, 90°, 105°, 120°, 135°, 150°, and 165°.

### Model predictions

The archive contains no OPJU data for 15°, 30°, or 60°. These files are model outputs and must not be treated as measurements:

- `predicted_missing_angles.csv`
- `predicted_missing_curves_centered.csv`
- `missing_angles_model_curves.png`
- `缺失角度_模型预测回线.png`

The predicted curves use the measured 45° curve shape as a deterministic template and scale it with the selected angular-amplitude model. No random measurement noise was added.

### Mixed analysis files

The following files contain both measured inputs and clearly labeled model-prediction sections:

- `SOT_results.xlsx`
- `SOT_角度依赖_实测提取与缺失角度模型.xlsx`
- `angular_amplitude_model.png`
- `翻转幅度_角度依赖_模型.png`
- `analysis_notes.txt`
- `分析说明.txt`

The ZIP archives are packaged copies of these result files. The original OPJU vertical-axis unit was not specified, so the resistance values are retained in the original numerical units.
