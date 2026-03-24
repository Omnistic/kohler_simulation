# Kohler Simulation
OpticStudio archive (ZAR) and macro (ZPL) for BMP generation for [Kohler interactive simulation](https://kohler-simulation.microscopybench.com/).
The 8,000 BMP files are converted to AVIF files that are displayed in the JavaScript, HTML app.
The files were generated using OpticStudio 2026 R1 (Synopsys).
## Archive (ZAR) Usage
The macro will automatically generate images for 20 steps for the field stop (field diaphragm), aperture stop (condenser diaphragm), and condenser (lens + diaphragm) axial position (total = 20 * 20 * 20 = 8,000 images).
It is possible to use the archive manually:
- The field stop is controlled by the multi-configuration operand 3 (APMX) in the Config 1, and updates automatically (macro sweeps from 20 to 5).
- The condenser axial position is controlled by Thickness 2, and updates automatically (macro sweeps from 250 to 130).
- The aperture stop is controlled by the multi-configuration operand 4 (APMX) in the Config 1, and **requires** a local optimization (Merit Function already implemented, run automatic cycles | macro sweeps from 36 to 6).
## Limitations And Future Work
Currently, the 8,000 AVIF frames represent 335MB on disk. The loading time is about 20 seconds with a fast internet network. An additional slider for the lateral position of the condenser with again 20 steps (for a relatively smooth animation) would bring the total to 8,000 * 20 = 160,000 images (total size in the range of 335 * 20 = 6.7GB), and is not viable at this point.
