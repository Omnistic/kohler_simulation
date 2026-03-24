# Kohler Simulation
OpticStudio archive (ZAR) and macro (ZPL) for BMP generation for [Kohler interactive simulation](https://kohler-simulation.microscopybench.com/).
The 8,000 BMP files are converted to AVIF files that are displayed in the JavaScript, HTML app.
## Archive (ZAR) Usage
The macro will automatically generate images for 20 steps for the field stop (field diaphragm), aperture stop (condenser diaphragm), and condenser (lens + diaphragm) axial position (total = 20 * 20 * 20 = 8,000 images).
It is possible to use the archive manually:
- The field stop is controlled by the multi-configuration operand 3 (APMX) in the Config 1, and updates automatically (macro sweeps from 20 to 5).
- The condenser axial position is controlled by Thickness 2, and updates automatically (macro sweeps from 250 to 130).
- The aperture stop is controlled by the multi-configuration operand 4 (APMX) in the Config 1, and **requires** a local optimization (Merit Function already implemented, run automatic cycles | macro sweeps from 36 to 6).
