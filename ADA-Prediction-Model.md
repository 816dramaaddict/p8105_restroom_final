Multiple Logistic Regression
================
Rita Wang
2024-12-07

MTA reports that there is 63 out of 423 subway stations provide
restrooms 7am - 7pm and in restroom_df that we imported from NYC Open
Data, only 1047 restroom were marked as in the location of subway out of
5 recorded restrooms.

    ## # weights:  48 (30 variable)
    ## initial  value 146.115434 
    ## iter  10 value 55.623097
    ## iter  20 value 54.643579
    ## iter  30 value 54.590588
    ## iter  40 value 54.264483
    ## iter  50 value 54.250649
    ## iter  60 value 54.105333
    ## final  value 54.105298 
    ## converged

    ## Call:
    ## multinom(formula = restroom_accessibility ~ restroom_latitude + 
    ##     restroom_longitude + restroom_changing_stations + restroom_open + 
    ##     station_latitude + station_longitude + entrance_type + staffing, 
    ##     data = restroom_subway_data)
    ## 
    ## Coefficients:
    ##                      (Intercept) restroom_latitude restroom_longitude
    ## Fully Accessible        13.09322        -44.518986          -51.73608
    ## Partially Accessible    16.87786          6.597743          -42.09849
    ##                      restroom_changing_stations restroom_open.L restroom_open.Q
    ## Fully Accessible                      0.6882738        9.258301        5.345283
    ## Partially Accessible                 -0.2384599       11.934446        6.890356
    ##                      station_latitude station_longitude entrance_type4
    ## Fully Accessible            45.850648          52.89934       19.29844
    ## Partially Accessible        -6.401506          42.45565      -12.21631
    ##                      entrance_type5 entrance_type6 entrance_type7 staffing.L
    ## Fully Accessible          25.222168       32.24590       15.90470   3.510139
    ## Partially Accessible      -7.487845      -26.49563      -17.85312  -2.186729
    ##                      staffing.Q staffing.C
    ## Fully Accessible      -6.005553  -8.185782
    ## Partially Accessible  19.399016   7.440258
    ## 
    ## Std. Errors:
    ##                      (Intercept) restroom_latitude restroom_longitude
    ## Fully Accessible     0.012725751          3.631205           1.859037
    ## Partially Accessible 0.004402801          3.828218           2.236096
    ##                      restroom_changing_stations restroom_open.L restroom_open.Q
    ## Fully Accessible                       1.386419      0.00899846     0.005195264
    ## Partially Accessible                   1.491436      0.00311325     0.001797436
    ##                      station_latitude station_longitude entrance_type4
    ## Fully Accessible             3.605981          2.133139      0.5060878
    ## Partially Accessible         3.842266          1.993631      0.5058369
    ##                      entrance_type5 entrance_type6 entrance_type7 staffing.L
    ## Fully Accessible          0.3434136   4.063777e-07      0.2903154  0.8500843
    ## Partially Accessible      0.3434104   2.145778e-11      0.2901591  0.9164712
    ##                       staffing.Q staffing.C
    ## Fully Accessible     0.006362873  0.2833614
    ## Partially Accessible 0.002201400  0.3054904
    ## 
    ## Residual Deviance: 108.2106 
    ## AIC: 156.2106

    ##                       Actual
    ## Predicted              Not Accessible Fully Accessible Partially Accessible
    ##   Not Accessible                    0                0                    0
    ##   Fully Accessible                  3              114                   14
    ##   Partially Accessible              0                0                    2

    ## [1] "Accuracy:  0.87218045112782"
