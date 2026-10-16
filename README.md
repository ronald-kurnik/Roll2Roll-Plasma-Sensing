# Roll to Roll Plasma Sensing
![R2R](R2R_Plasma_Sensing.png)
![Scope](ScopePrintToFigure.png)

## What the Roll-to-Roll Simulink simulation accomplishes
The purpose of the model is to generate a realistic, imperfect sensor time series that looks like something you would actually get from an inline plasma sensor on a moving web.
Here’s the logic step by step:
1. Create a “True” Material Property

We start with a clean thickness signal (sine wave + step).
This represents the real physical thickness of the coating as it moves along the production line.

2. Pass it through Sensor Effects

Transport Delay → accounts for the fact that the material is moving (the sensor sees the property with a time lag).
Sensor Dynamics (low-pass filter) → models the finite response time / spot size of the real sensor.

3. Add Realistic Artifacts

All real sensors have noiseDriftSlow baseline drift (temperature change, sensor aging, etc.)
Very common in industrial sensorsSpikeSudden outliers / electrical glitchesHappens in real factory environments

4. What to do with the final signal (sensor_raw)
The contaminated signal is intentionally dirty. You then use it to demonstrate the detection and removal/correction of  the drift, spikes, and noise.
