# AppADay 088 &middot; Brew Math

A single-screen homebrew calculator. Enter your original and final gravity and read **ABV**, **apparent and real attenuation**, and rough **calories** per serving. A mode toggle switches between hydrometer (specific gravity) and refractometer (Brix) readings, applying the wort correction factor and the Terrill cubic alcohol correction so refractometer final gravities come out honest.

**Category:** U (Utility) &middot; **AI:** No &middot; **Stack:** Vanilla HTML / CSS / JS, single file.

## What it does

- **ABV** using the accurate `(76.08 * (OG - FG) / (1.775 - OG)) * (FG / 0.794)` formula.
- **Apparent attenuation** from measured gravity, `(OG - FG) / (OG - 1)`.
- **Real attenuation** via degrees-Plato extracts, backing the alcohol skew out for the honest figure.
- **Calories** combining alcohol and residual sugar, shown per 12 oz and per 16 oz pint.
- **Refractometer mode** with an adjustable wort correction factor (default 1.04) and automatic alcohol correction, so a final Brix reading is turned into a true final gravity.
- **One-tap WCF calibration.** Enter a refractometer Brix reading and the matching temperature-corrected hydrometer OG from one pre-yeast sample, and it solves your instrument's wort factor and fills the field. The solve is the exact inverse of the Brix-to-gravity relation, so re-entering that reading reproduces your known OG.

## Using it correctly

**Hydrometer mode.** Enter each reading as a full specific gravity value such as `1.052` and `1.010`, not the gravity points or a Plato number. Temperature-correct the reading to the hydrometer's calibration temperature (usually 60&deg;F / 20&deg;C) first, or ABV will drift.

**Refractometer mode.** Enter both readings in degrees Brix. Set the wort correction factor, or tap **Calibrate** and let the app solve it: enter one refractometer reading with the temperature-corrected hydrometer OG from the same pre-yeast sample and it fills the factor for you. Leave it at 1.04 if uncalibrated. The app corrects the final Brix for alcohol automatically and shows the derived OG and FG so you can sanity-check them.

Built-in guards reject a final gravity that is not lower than the original, catch gravity-points entered by mistake, and flag an out-of-range wort factor. Results persist locally between visits and are estimates for planning and label copy, not lab measurements.

Part of [AppADay](https://augustineiacopelli.github.io/appaday/) by Augustine Iacopelli. One complete, functional, mobile-friendly web app, shipped every day.
