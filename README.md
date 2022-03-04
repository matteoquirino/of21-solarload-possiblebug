# of21-solarload-possiblebug
Solar load test case to verify if there is bug.

## simplecube-nosolarload
Two regions: "space" represent deep space thus vaccuum and blackbody at 0 K on the boundaries. "cube" aluminum cube with temperature fixed at one end. The radiative load is introduced modifying "qro" in 0/space/qr setting it to "uniform 1400".
Both regions have dimensions 1 m x 1 m x 1 m. The cube is adiabatic on all boundaries except for the one opposite to the common boundary with space region which is fixed at 273 K. The common boundary is set as done in the tutorial "multiRegionRadiation".

Using emissivity and absorptivity equal to 0.7 the analytical solution for face recieving sunlight is 276.4 K. The solution computed by chtMultiRegionSimpleFoam is equal to the analytical one.

The analytical solution is given by the equation:
0 = q_sun * alpha * A + epsilon * sigma * (Tspace^4 - Tsurface^4) + k * A/L * (Tfix - Tsurface)

## simplecube-solarload
Geometry identical to the previous case, but sun radiation is introduced using solarLoad utility with constant direction and sun flux fixed at 1400 W/m2. With emissivity and absorptivity equal to 0.7 The solution computed by chtMultiRegionSimpleFoam is 275 K.

Small difference but not justified since with the other case the analytical solution is catached, plus testing other cases the difference is bigger.

