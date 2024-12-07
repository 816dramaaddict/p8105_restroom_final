ADA Accessibility Prediction
================
Rita Wang
2024-12-07

| y.level              | term                       |    estimate | std.error |     statistic |   p.value |
|:---------------------|:---------------------------|------------:|----------:|--------------:|----------:|
| Fully Accessible     | (Intercept)                |  13.0932151 | 0.0127258 |  1.028876e+03 | 0.0000000 |
| Fully Accessible     | restroom_latitude          | -44.5189861 | 3.6312052 | -1.226011e+01 | 0.0000000 |
| Fully Accessible     | restroom_longitude         | -51.7360783 | 1.8590365 | -2.782951e+01 | 0.0000000 |
| Fully Accessible     | restroom_changing_stations |   0.6882738 | 1.3864191 |  4.964400e-01 | 0.6195840 |
| Fully Accessible     | restroom_open.L            |   9.2583012 | 0.0089985 |  1.028876e+03 | 0.0000000 |
| Fully Accessible     | restroom_open.Q            |   5.3452827 | 0.0051953 |  1.028876e+03 | 0.0000000 |
| Fully Accessible     | station_latitude           |  45.8506478 | 3.6059814 |  1.271516e+01 | 0.0000000 |
| Fully Accessible     | station_longitude          |  52.8993405 | 2.1331388 |  2.479883e+01 | 0.0000000 |
| Fully Accessible     | entrance_type4             |  19.2984366 | 0.5060878 |  3.813259e+01 | 0.0000000 |
| Fully Accessible     | entrance_type5             |  25.2221681 | 0.3434136 |  7.344545e+01 | 0.0000000 |
| Fully Accessible     | entrance_type6             |  32.2458999 | 0.0000004 |  7.934958e+07 | 0.0000000 |
| Fully Accessible     | entrance_type7             |  15.9046967 | 0.2903154 |  5.478420e+01 | 0.0000000 |
| Fully Accessible     | staffing.L                 |   3.5101394 | 0.8500843 |  4.129166e+00 | 0.0000364 |
| Fully Accessible     | staffing.Q                 |  -6.0055529 | 0.0063629 | -9.438429e+02 | 0.0000000 |
| Fully Accessible     | staffing.C                 |  -8.1857815 | 0.2833614 | -2.888813e+01 | 0.0000000 |
| Partially Accessible | (Intercept)                |  16.8778559 | 0.0044028 |  3.833436e+03 | 0.0000000 |
| Partially Accessible | restroom_latitude          |   6.5977432 | 3.8282184 |  1.723450e+00 | 0.0848072 |
| Partially Accessible | restroom_longitude         | -42.0984929 | 2.2360956 | -1.882679e+01 | 0.0000000 |
| Partially Accessible | restroom_changing_stations |  -0.2384599 | 1.4914359 | -1.598861e-01 | 0.8729708 |
| Partially Accessible | restroom_open.L            |  11.9344464 | 0.0031133 |  3.833436e+03 | 0.0000000 |
| Partially Accessible | restroom_open.Q            |   6.8903558 | 0.0017974 |  3.833436e+03 | 0.0000000 |
| Partially Accessible | station_latitude           |  -6.4015063 | 3.8422657 | -1.666076e+00 | 0.0956983 |
| Partially Accessible | station_longitude          |  42.4556487 | 1.9936307 |  2.129564e+01 | 0.0000000 |
| Partially Accessible | entrance_type4             | -12.2163142 | 0.5058369 | -2.415070e+01 | 0.0000000 |
| Partially Accessible | entrance_type5             |  -7.4878451 | 0.3434104 | -2.180437e+01 | 0.0000000 |
| Partially Accessible | entrance_type6             | -26.4956256 | 0.0000000 | -1.234779e+12 | 0.0000000 |
| Partially Accessible | entrance_type7             | -17.8531214 | 0.2901591 | -6.152873e+01 | 0.0000000 |
| Partially Accessible | staffing.L                 |  -2.1867293 | 0.9164712 | -2.386032e+00 | 0.0170313 |
| Partially Accessible | staffing.Q                 |  19.3990161 | 0.0022014 |  8.812125e+03 | 0.0000000 |
| Partially Accessible | staffing.C                 |   7.4402576 | 0.3054904 |  2.435513e+01 | 0.0000000 |

Model Summary

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
