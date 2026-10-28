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

## Clean standard model curves for 0°–60°

The 0°/15°/30°/45°/60° model workbooks use a deterministic two-branch SOT switching model rather than noisy measured-template interpolation. Branch 1 switches from the low plateau to the high plateau near `+Ic`; branch 2 switches from high to low near `−Ic`. The amplitude follows the previously selected angular trend, while `Ic` varies smoothly with angle. No random noise or endpoint fluctuations are added. These five files remain model predictions, not raw measurements.

The curve form is:

`R1(I) = Rlow + A·sigmoid((I−Ic)/w)`

`R2(I) = Rlow + A·sigmoid((I+Ic)/w)`

where `A` is the angle-dependent flip amplitude, `Ic` is the smooth angle-dependent switching threshold, and `w` is the narrow transition width.

## Visualization-shifted wide table

When plotting the raw wide table, the 90°–165° curves can overlap because their original baselines are close. For a clearer stacked display, use:

- `SOT_all_angles_wide_shifted.xlsx`
- `SOT_all_angles_wide_shifted.csv`
- `SOT_all_angles_wide_shifted.png`
- `SOT_all_angles_visual_offsets.csv`

Only the 90°–165° columns receive angle-specific constant vertical offsets. The first column and all switching shapes are unchanged. These shifted values are for visualization only and must not be used for quantitative resistance, amplitude, or physical-parameter fitting; use `SOT_all_angles_wide.xlsx` for quantitative work.

## Display-normalized wide table

For a figure where the 0° curve is centered near 10 and the 15° curve near 7, use:

- `SOT_all_angles_wide_display.xlsx`
- `SOT_all_angles_wide_display.csv`
- `SOT_all_angles_display.png`
- `SOT_all_angles_display_transform.csv`

This display table shifts the angle baselines and applies a visual amplitude floor to the small 90°–165° loops so their switching shape remains visible. It is for plotting only. Do not use it for quantitative fitting; use `SOT_all_angles_wide.xlsx` instead.

## Clean all-angle display model

For a readable all-angle figure in which the post-90° switching shapes remain visible, use:

- `SOT_all_angles_clean_display.xlsx`
- `SOT_all_angles_clean_display.csv`
- `SOT_all_angles_clean_display.png`
- `SOT_all_angles_clean_display_parameters.csv`

This is a clean display model for all 12 angles. It uses standard two-branch sigmoid switching curves and a smooth decreasing display-amplitude envelope after 90°. It is not a replacement for the raw measured data and must not be used for quantitative fitting.

## Clean all-angle display model V2

`SOT_all_angles_clean_display_v2.xlsx`/`.csv` and `SOT_all_angles_clean_display_v2.png` use a stronger post-90° display-amplitude envelope so those loops remain visibly separated on one shared Y axis. This is a visualization-only model; it does not represent the raw post-90° measured amplitudes.
