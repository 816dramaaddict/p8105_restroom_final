ADA Accessibility Prediction
================
Rita Wang
2024-12-07

**Fully accessible model:**

*fully ADA accessible* = 13.09322 + (-44.518986 x restroom_latitude) +
(-51.73608 x restroom_longitude) + (0.6882738 x
restroom_changing_stations) + (9.258301 x restroom_open.L) + (5.345283 x
restroom_open.Q) + (45.850648 x station_latitude) + (52.89934 x
station_longitude) + (19.29844 x entrance_type4) + (25.222168 x
entrance_type5) + (32.24590 x entrance_type6) + (15.90470 x
entrance_type7) + (3.510139 x staffing.L) + (-6.005553 x staffing.Q) +
(-8.185782 x staffing.C)

**Partially accessible model:**

*partially ADA accessible* = 16.87786 + (6.597743 x restroom_latitude) +
(-42.09849 x restroom_longitude) + (-0.2384599 x
restroom_changing_stations) + (11.934446 x restroom_open.L) + (6.890356
x restroom_open.Q) + (-6.401506 x station_latitude) + (42.45565 x
station_longitude) + (-12.21631 x entrance_type4) + (-7.487845 x
entrance_type5) + (-26.49563 x entrance_type6) + (-17.85312 x
entrance_type7) + (-2.186729 x staffing.L) + (19.399016 x staffing.Q) +
(7.440258 x staffing.C)

When testing the prediction model on the public restroom and train
station data, there is an approximate of 87.218045112782 %.
