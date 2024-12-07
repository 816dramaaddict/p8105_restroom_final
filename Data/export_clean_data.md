export_clean_data
================
2024-12-07

# Import Data

We import the restroom data from NYC Open Data:
<https://data.cityofnewyork.us/City-Government/Public-Restrooms/i7jb-7jku/about_data>
and subway data from the P8105 course website Homework 2 (Problem 1):
<https://p8105.com/homework_2.html>

Then we use `skimr::skim()` to check variables of both datasets.

``` r
subway_dirty = read_csv("NYC_Transit_Subway_Entrance_And_Exit_Data.csv") %>% 
  janitor::clean_names()

restroom_dirty = read_csv("Public_Restrooms_20241203.csv") %>% 
  janitor::clean_names()

# View subway_dirty
skimr::skim(subway_dirty)
```

|                                                  |              |
|:-------------------------------------------------|:-------------|
| Name                                             | subway_dirty |
| Number of rows                                   | 1868         |
| Number of columns                                | 32           |
| \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_   |              |
| Column type frequency:                           |              |
| character                                        | 22           |
| logical                                          | 2            |
| numeric                                          | 8            |
| \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ |              |
| Group variables                                  | None         |

Data summary

**Variable type: character**

| skim_variable      | n_missing | complete_rate | min | max | empty | n_unique | whitespace |
|:-------------------|----------:|--------------:|----:|----:|------:|---------:|-----------:|
| division           |         0 |          1.00 |   3 |   3 |     0 |        3 |          0 |
| line               |         0 |          1.00 |   5 |  17 |     0 |       36 |          0 |
| station_name       |         0 |          1.00 |   4 |  39 |     0 |      356 |          0 |
| route1             |         0 |          1.00 |   1 |   2 |     0 |       24 |          0 |
| route2             |       848 |          0.55 |   1 |   2 |     0 |       20 |          0 |
| route3             |      1374 |          0.26 |   1 |   2 |     0 |       18 |          0 |
| route4             |      1547 |          0.17 |   1 |   1 |     0 |       13 |          0 |
| route5             |      1630 |          0.13 |   1 |   1 |     0 |       12 |          0 |
| route6             |      1741 |          0.07 |   1 |   1 |     0 |        7 |          0 |
| route7             |      1788 |          0.04 |   1 |   2 |     0 |        7 |          0 |
| entrance_type      |         0 |          1.00 |   4 |   9 |     0 |        7 |          0 |
| entry              |         0 |          1.00 |   2 |   3 |     0 |        2 |          0 |
| exit_only          |      1812 |          0.03 |   3 |   3 |     0 |        1 |          0 |
| vending            |         0 |          1.00 |   2 |   3 |     0 |        2 |          0 |
| staffing           |         0 |          1.00 |   4 |   6 |     0 |        4 |          0 |
| staff_hours        |      1828 |          0.02 |  16 |  33 |     0 |       16 |          0 |
| ada_notes          |      1793 |          0.04 |   5 |  17 |     0 |       10 |          0 |
| north_south_street |        29 |          0.98 |   4 |  23 |     0 |      307 |          0 |
| east_west_street   |        35 |          0.98 |   6 |  24 |     0 |      352 |          0 |
| corner             |        32 |          0.98 |   1 |   4 |     0 |        8 |          0 |
| station_location   |         0 |          1.00 |  20 |  23 |     0 |      472 |          0 |
| entrance_location  |         0 |          1.00 |  22 |  23 |     0 |     1857 |          0 |

**Variable type: logical**

| skim_variable  | n_missing | complete_rate | mean | count               |
|:---------------|----------:|--------------:|-----:|:--------------------|
| ada            |         0 |             1 | 0.25 | FAL: 1400, TRU: 468 |
| free_crossover |         0 |             1 | 0.78 | TRU: 1448, FAL: 420 |

**Variable type: numeric**

| skim_variable | n_missing | complete_rate | mean | sd | p0 | p25 | p50 | p75 | p100 | hist |
|:---|---:|---:|---:|---:|---:|---:|---:|---:|---:|:---|
| station_latitude | 0 | 1.00 | 40.73 | 0.07 | 40.58 | 40.69 | 40.73 | 40.77 | 40.90 | ▂▅▇▃▂ |
| station_longitude | 0 | 1.00 | -73.94 | 0.06 | -74.03 | -73.99 | -73.96 | -73.91 | -73.76 | ▇▆▃▂▁ |
| route8 | 1820 | 0.03 | 2.98 | 1.94 | 1.00 | 1.00 | 4.00 | 5.00 | 5.00 | ▇▁▁▂▇ |
| route9 | 1840 | 0.01 | 2.54 | 1.17 | 2.00 | 2.00 | 2.00 | 2.00 | 5.00 | ▇▁▁▁▂ |
| route10 | 1845 | 0.01 | 3.00 | 0.00 | 3.00 | 3.00 | 3.00 | 3.00 | 3.00 | ▁▁▇▁▁ |
| route11 | 1845 | 0.01 | 7.00 | 0.00 | 7.00 | 7.00 | 7.00 | 7.00 | 7.00 | ▁▁▇▁▁ |
| entrance_latitude | 0 | 1.00 | 40.73 | 0.07 | 40.58 | 40.69 | 40.73 | 40.77 | 40.90 | ▂▅▇▃▂ |
| entrance_longitude | 0 | 1.00 | -73.86 | 3.42 | -74.03 | -73.99 | -73.96 | -73.91 | 73.99 | ▇▁▁▁▁ |

``` r
# View restroom_dirty
skimr::skim(restroom_dirty)
```

|                                                  |                |
|:-------------------------------------------------|:---------------|
| Name                                             | restroom_dirty |
| Number of rows                                   | 1047           |
| Number of columns                                | 14             |
| \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_   |                |
| Column type frequency:                           |                |
| character                                        | 12             |
| numeric                                          | 2              |
| \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ |                |
| Group variables                                  | None           |

Data summary

**Variable type: character**

| skim_variable      | n_missing | complete_rate | min | max | empty | n_unique | whitespace |
|:-------------------|----------:|--------------:|----:|----:|------:|---------:|-----------:|
| facility_name      |         0 |          1.00 |   4 |  82 |     0 |     1021 |          0 |
| location_type      |         0 |          1.00 |   4 |  28 |     0 |        5 |          0 |
| operator           |         0 |          1.00 |   3 |  50 |     0 |       34 |          0 |
| status             |         0 |          1.00 |   6 |  23 |     0 |        4 |          0 |
| open               |        66 |          0.94 |   6 |  10 |     0 |        3 |          0 |
| hours_of_operation |        48 |          0.95 |   7 | 199 |     0 |       96 |          0 |
| accessibility      |       225 |          0.79 |  14 |  20 |     0 |        3 |          0 |
| restroom_type      |       186 |          0.82 |  25 |  48 |     0 |        4 |          0 |
| changing_stations  |       836 |          0.20 |   2 |  47 |     0 |        4 |          0 |
| additional_notes   |       983 |          0.06 |  23 | 102 |     0 |       13 |          0 |
| website            |       821 |          0.22 |  34 |  91 |     0 |      216 |          0 |
| location           |         0 |          1.00 |  22 |  28 |     0 |     1038 |          0 |

**Variable type: numeric**

| skim_variable | n_missing | complete_rate | mean | sd | p0 | p25 | p50 | p75 | p100 | hist |
|:---|---:|---:|---:|---:|---:|---:|---:|---:|---:|:---|
| latitude | 0 | 1 | 40.73 | 0.09 | 40.50 | 40.67 | 40.73 | 40.79 | 40.90 | ▁▅▇▆▅ |
| longitude | 0 | 1 | -73.92 | 0.09 | -74.25 | -73.97 | -73.93 | -73.86 | -73.71 | ▁▁▇▇▂ |

# Clean Variable

``` r
subway_cleaned <- subway_dirty %>% 
  mutate(
    entrance_type = factor(
      entrance_type,
      levels = c("Stair", "Easement", "Door", "Walkway", "Escalator", "Ramp", "Elevator")
    )
  ) %>% 
  mutate(
    staffing = factor(
      staffing,
      levels = c("NONE", "Spc Ev", "PART", "FULL")
    )
  ) %>% 
  dplyr::select(
    division, line, station_name, station_latitude, station_longitude, 
    entrance_type, vending, staffing, ada, free_crossover, station_location
  ) %>% 
  st_as_sf(coords = c("station_longitude", "station_latitude"), crs = 4326) %>%
  distinct(station_name, .keep_all = TRUE)

# Convert subway data to sf object
subway_sf <- st_sf(subway_cleaned, crs = 4326)
```

For subway data, we factor character variables `entrance_type` and
`staffing` into categorical variables and select variable like
`station_latitude`, `station_longitude`, `ada`, etc for future analysis.

After cleaning, `subway_cleaned` contains 356 rows and 10 columns.

``` r
restroom_cleaned <- restroom_dirty %>% 
  dplyr::select(
    -website, -operator, -hours_of_operation, -additional_notes
  ) %>% 
  rename(
    restroom_latitude = latitude,
    restroom_longitude = longitude,
    restroom_location = location
  ) %>% 
  mutate(
    restroom_latitude = as.numeric(restroom_latitude),
    restroom_longitude = as.numeric(restroom_longitude),
    restroom_open = factor(
      open,
      levels = c("Future", "Seasonal", "Year Round"),
      ordered = TRUE
    ),
    restroom_accessibility = factor(
      accessibility,
      levels = c("Not Accessible", "Partially Accessible", "Fully Accessible"),
      ordered = TRUE
    ),
    restroom_changing_stations = case_when(
      changing_stations %in% c("Yes, in single-stall all gender restroom only",
                                "Yes, in women's restroom only",
                                "Yes") ~ 1,
    changing_stations %in% c("No", NA) ~ 0
),
    restroom_status = case_when(
      status %in% c("Not Operational",
                    "Closed for Construction",
                    "Closed") ~ 0,
      status == "Operational" ~ 1
    )
  ) %>% 
  dplyr::select(
    -open, -accessibility, -changing_stations, -status
  )

# Convert dataframe to sf for spatial operations
restroom_sf <- st_as_sf(restroom_cleaned, coords = c("restroom_longitude", "restroom_latitude"), crs = 4326)

# Filter restrooms near transit
restroom_near_transit <- restroom_cleaned %>% 
  filter(location_type == 'Transit')

subway_with_restrooms <- st_join(subway_sf, restroom_sf, join = st_nearest_feature)
```

For restroom data, we factor the character variables (`status`, ) into
binary and categorical variables.

# Export clean data

``` r
save_restroom_path = "cleaned_restroom_data.csv"
write_csv(restroom_sf, save_restroom_path, na="")

save_subway_path = "cleaned_subway_data.csv"
write_csv(subway_sf, save_subway_path, na="")

save_subway_restroom_path = "cleaned_subway_restroom_data.csv"
write_csv(subway_with_restrooms, save_subway_restroom_path, na="")
```
