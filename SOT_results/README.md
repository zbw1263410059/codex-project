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

The predicted amplitudes retain the selected angular-amplitude model. Their curve shapes are angle-dependent: the normalized measured 0°, 45°, and 75° loop shapes are blended by angle (0°→45° for 15°/30°; 45°→75° for 60°), so the model curves are distinct while remaining smoothly related. No random measurement noise was added.

### Mixed analysis files

The following files contain both measured inputs and clearly labeled model-prediction sections:

- `SOT_results.xlsx`
- `SOT_角度依赖_实测提取与缺失角度模型.xlsx`
- `angular_amplitude_model.png`
- `翻转幅度_角度依赖_模型.png`
- `analysis_notes.txt`
- `分析说明.txt`

The ZIP archives are packaged copies of these result files. The original OPJU vertical-axis unit was not specified, so the resistance values are retained in the original numerical units.

## Standardized 52-point angle files

The following files were generated after using the uploaded `165度.xlsx` as a point-count and current-sequence template:

- `SOT_0deg.xlsx`
- `SOT_15deg.xlsx`
- `SOT_30deg.xlsx`
- `SOT_45deg.xlsx`
- `SOT_60deg.xlsx`
- `generated_angle_xlsx.zip`
- `generated_angle_files_manifest.csv`

Each workbook contains 52 numeric points in `Sheet1` (two 26-point branches) and an `说明` sheet. These five files are **model-generated standardized data, not raw measurements**. The 15°, 30°, and 60° angles had no source OPJU measurements in the uploaded archive; the 0° and 45° files were also re-generated to use the common 52-point sequence. The manifest records the model amplitudes and source status.

## Remaining measured angles and stacked summary

The standardized measured-angle workbooks are:

- `SOT_75deg.xlsx`
- `SOT_90deg.xlsx`
- `SOT_105deg.xlsx`
- `SOT_120deg.xlsx`
- `SOT_135deg.xlsx`
- `SOT_150deg.xlsx`
- `SOT_165deg.xlsx`

They use the OPJU curves from the uploaded archive and interpolate each selected measured loop to the common 52-point current sequence. They remain labeled as measured resamples, not new measurements.

For comparison across all 12 angles:

- `SOT_all_angles_52point.xlsx` contains one sheet per angle plus a manifest.
- `SOT_all_angles_52point_long.csv` is a long-form table for plotting.
- `SOT_all_angles_stacked.png` is the stacked comparison figure.
- `all_angles_52point_manifest.csv` records the source status and point count.

In the stacked summary, 0°/15°/30°/45°/60° are model-standardized files; 75°/90°/105°/120°/135°/150°/165° are measured OPJU resamples.

## Angle-dependent model shapes

The 0°/15°/30°/45°/60° standardized model workbooks and the stacked figure use angle-dependent loop-shape templates. They no longer reuse one identical loop shape at all five angles. The amplitudes remain tied to the previously extracted angular trend, while the shape changes are constrained by normalized measured 0°, 45°, and 75° curves.
