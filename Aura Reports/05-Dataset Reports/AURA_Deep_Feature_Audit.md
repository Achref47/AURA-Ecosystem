# AURA Deep Feature & Column Audit Report
**Generated on:** 2026-07-01 12:56:48
**Target Directory:** `C:\Users\achre\OneDrive\Desktop\Aura\Aura Datasets`
*(Note: Deep profiling utilizes a randomized sample of up to 100,000 rows per dataset for memory efficiency)*

---

## 📁 System Component: `Aura -Dataset -First Version`

### 📄 Dataset: **aura_master_dataset_Version 1.csv**
- **Sample Analyzed:** 100,000 rows
- **Total Features:** 152
| Feature Name | Data Type | Missing (%) | Unique Values | Distribution / Top Values |
|---|---|---|---|---|
| `price` | `float64` | 0.00% | 4,186 | Range: [10250.00 ➔ 9950000.00] | Mean: 358221.50 |
| `district` | `object` | 0.00% | 25 | Top: 'Lisboa': 23328 | 'Porto': 15967 |
| `city` | `object` | 0.00% | 271 | Top: 'Lisboa': 6355 | 'Sintra': 4105 |
| `town` | `object` | 0.00% | 2,232 | Top: 'Cascais e Estoril': 1084 | 'Portimão': 888 |
| `property_type` | `object` | 0.01% | 21 | Top: 'Apartment': 32531 | 'House': 27876 |
| `energy_certificate` | `object` | 0.00% | 13 | Top: 'NC': 44778 | 'C': 12261 |
| `gross_area` | `float64` | 74.34% | 2,225 | Range: [0.00 ➔ 12750000.00] | Mean: 2843.61 |
| `total_area` | `float64` | 4.83% | 7,136 | Range: [0.00 ➔ 61420071105.00] | Mean: 684074.57 |
| `parking_slots` | `float64` | 0.03% | 4 | Range: [0.00 ➔ 3.00] | Mean: 0.60 |
| `has_parking` | `float64` | 37.65% | 2 | Binary/Flag: {0.0: 34182, 1.0: 28169} |
| `floor_raw` | `object` | 74.30% | 19 | Top: 'Ground Floor': 6470 | '1st Floor': 5484 |
| `construction_year` | `float64` | 34.47% | 124 | Range: [1900.00 ➔ 2025.00] | Mean: 1988.42 |
| `energy_efficiency_level` | `object` | 0.00% | 12 | Top: 'Unknown': 62381 | 'NC': 18515 |
| `publish_date` | `object` | 96.46% | 3,523 | Top: '2023-05-04 11:07:23.047': 2 | '2023-05-04 11:14:52.360': 2 |
| `garage` | `float64` | 62.38% | 2 | Binary/Flag: {0.0: 31412, 1.0: 6207} |
| `elevator` | `float64` | 0.03% | 2 | Binary/Flag: {0.0: 76448, 1.0: 23522} |
| `charging_flag` | `float64` | 62.38% | 2 | Binary/Flag: {0.0: 34393, 1.0: 3226} |
| `rooms` | `float64` | 41.31% | 54 | Range: [0.00 ➔ 2751.00] | Mean: 3.10 |
| `bedrooms` | `float64` | 74.93% | 21 | Range: [0.00 ➔ 21.00] | Mean: 2.68 |
| `wc` | `float64` | 64.07% | 23 | Range: [0.00 ➔ 59.00] | Mean: 0.36 |
| `condition` | `object` | 89.44% | 6 | Top: 'New': 3794 | 'Good condition': 2723 |
| `living_area` | `float64` | 23.00% | 2,865 | Range: [0.00 ➔ 5429000.00] | Mean: 1639.46 |
| `lot_size` | `float64` | 75.66% | 5,777 | Range: [0.00 ➔ 992301000.00] | Mean: 72321.33 |
| `built_area` | `float64` | 85.05% | 5,253 | Range: [0.00 ➔ 12750000.00] | Mean: 3950.45 |
| `bathrooms` | `float64` | 3.67% | 40 | Range: [0.00 ➔ 90.00] | Mean: 1.49 |
| `gross_area_missing` | `float64` | 0.00% | 2 | Binary/Flag: {1.0: 74341, 0.0: 25659} |
| `total_area_missing` | `float64` | 0.00% | 2 | Binary/Flag: {0.0: 95171, 1.0: 4829} |
| `parking_slots_missing` | `float64` | 0.00% | 2 | Binary/Flag: {0.0: 99857, 1.0: 143} |
| `construction_year_missing` | `float64` | 0.00% | 2 | Binary/Flag: {0.0: 65532, 1.0: 34468} |
| `rooms_missing` | `float64` | 0.00% | 2 | Binary/Flag: {0.0: 58687, 1.0: 41313} |
| `bedrooms_missing` | `float64` | 0.00% | 2 | Binary/Flag: {1.0: 74931, 0.0: 25069} |
| `wc_missing` | `float64` | 0.00% | 2 | Binary/Flag: {1.0: 64067, 0.0: 35933} |
| `living_area_missing` | `float64` | 0.00% | 2 | Binary/Flag: {0.0: 76999, 1.0: 23001} |
| `lot_size_missing` | `float64` | 0.00% | 2 | Binary/Flag: {1.0: 75662, 0.0: 24338} |
| `built_area_missing` | `float64` | 0.00% | 2 | Binary/Flag: {1.0: 85049, 0.0: 14951} |
| `bathrooms_missing` | `float64` | 0.00% | 2 | Binary/Flag: {0.0: 96330, 1.0: 3670} |
| `property_type_missing` | `float64` | 0.00% | 2 | Binary/Flag: {0.0: 99985, 1.0: 15} |
| `energy_certificate_missing` | `float64` | 0.00% | 2 | Binary/Flag: {0.0: 99987, 1.0: 13} |
| `energy_efficiency_level_missing` | `float64` | 0.00% | 2 | Binary/Flag: {1.0: 62381, 0.0: 37619} |
| `floor_raw_missing` | `float64` | 0.00% | 2 | Binary/Flag: {1.0: 74303, 0.0: 25697} |
| `garage_missing` | `float64` | 0.00% | 2 | Binary/Flag: {1.0: 62381, 0.0: 37619} |
| `elevator_missing` | `float64` | 0.00% | 2 | Binary/Flag: {0.0: 99970, 1.0: 30} |
| `charging_flag_missing` | `float64` | 0.00% | 2 | Binary/Flag: {1.0: 62381, 0.0: 37619} |
| `condition_missing` | `float64` | 0.00% | 2 | Binary/Flag: {1.0: 89442, 0.0: 10558} |
| `town_missing` | `float64` | 0.00% | 2 | Binary/Flag: {0.0: 99998, 1.0: 2} |
| `has_parking_missing` | `float64` | 0.00% | 2 | Binary/Flag: {0.0: 62351, 1.0: 37649} |
| `floor_level` | `float64` | 81.82% | 10 | Range: [1.00 ➔ 10.00] | Mean: 2.79 |
| `publish_year` | `float64` | 96.46% | 6 | Range: [2018.00 ➔ 2024.00] | Mean: 2023.54 |
| `publish_month` | `float64` | 96.46% | 12 | Range: [1.00 ➔ 12.00] | Mean: 4.84 |
| `publish_quarter` | `object` | 0.00% | 19 | Top: 'NaT': 96460 | '2024Q1': 1536 |
| `district_key` | `object` | 0.00% | 25 | Top: 'lisboa': 23328 | 'porto': 15967 |
| `city_key` | `object` | 0.00% | 271 | Top: 'lisboa': 6355 | 'sintra': 4105 |
| `town_key` | `object` | 0.00% | 2,230 | Top: 'cascais-e-estoril': 1084 | 'portimo': 888 |
| `property_region_key` | `object` | 0.00% | 25 | Top: 'lisboa': 23328 | 'porto': 15967 |
| `listing_date` | `object` | 0.00% | 3,525 | Top: '2000-01-01': 96444 | '2000-01-01 00:00:00.000': 16 |
| `listing_year` | `int64` | 0.00% | 7 | Range: [2000.00 ➔ 2024.00] | Mean: 2000.83 |
| `listing_month` | `int64` | 0.00% | 12 | Range: [1.00 ➔ 12.00] | Mean: 1.14 |
| `property_uid` | `uint64` | 0.00% | 38,622 | Range: [970612402881219.00 ➔ 18446088177625618432.00] | Mean: 9161208861231230976.00 |
| `merge_date` | `object` | 0.00% | 3,525 | Top: '2000-01-01': 96444 | '2000-01-01 00:00:00.000': 16 |
| `merge_year` | `int64` | 0.00% | 7 | Range: [2000.00 ➔ 2024.00] | Mean: 2000.83 |
| `fusion_region_key` | `object` | 0.00% | 25 | Top: 'lisboa': 23328 | 'porto': 15967 |
| `context_date` | `object` | 97.02% | 23 | Top: '2024-01-12': 1783 | '2023-01-12': 916 |
| `cal_sale_year` | `float64` | 97.02% | 6 | Range: [2018.00 ➔ 2024.00] | Mean: 2023.52 |
| `cal_sale_month` | `float64` | 97.02% | 11 | Range: [2.00 ➔ 12.00] | Mean: 11.87 |
| `cal_sale_price_per_sqm` | `float64` | 97.02% | 91 | Range: [634.00 ➔ 4279.00] | Mean: 2495.74 |
| `cal_sale_price_index_base100` | `float64` | 97.02% | 93 | Range: [92.15 ➔ 331.96] | Mean: 242.20 |
| `cal_sale_price_change_1m` | `float64` | 97.02% | 92 | Range: [-0.02 ➔ 0.05] | Mean: 0.01 |
| `cal_sale_price_change_3m` | `float64` | 97.02% | 93 | Range: [-0.02 ➔ 0.14] | Mean: 0.03 |
| `cal_sale_price_change_12m` | `float64` | 97.02% | 93 | Range: [-0.04 ➔ 0.21] | Mean: 0.09 |
| `cal_sale_price_ma_3` | `float64` | 97.02% | 93 | Range: [628.00 ➔ 4218.67] | Mean: 2464.30 |
| `cal_sale_price_ma_12` | `float64` | 97.02% | 92 | Range: [645.83 ➔ 4102.50] | Mean: 2394.12 |
| `cal_sale_market_momentum_score` | `float64` | 97.02% | 93 | Range: [-0.03 ➔ 0.18] | Mean: 0.06 |
| `cal_sale_market_pressure_score` | `float64` | 97.02% | 93 | Range: [-0.03 ➔ 0.18] | Mean: 0.07 |
| `cal_sale_price_volatility_12m` | `float64` | 97.02% | 93 | Range: [5.79 ➔ 143.66] | Mean: 63.43 |
| `cal_sale_price_type_weight` | `float64` | 97.02% | 1 | Binary/Flag: {1.0: 2980} |
| `cal_sale_is_sale` | `float64` | 97.02% | 1 | Binary/Flag: {1.0: 2980} |
| `cal_sale_is_rental` | `float64` | 97.02% | 1 | Binary/Flag: {0.0: 2980} |
| `cal_rental_year` | `float64` | 97.11% | 6 | Range: [2018.00 ➔ 2024.00] | Mean: 2023.52 |
| `cal_rental_month` | `float64` | 97.11% | 11 | Range: [2.00 ➔ 12.00] | Mean: 11.86 |
| `cal_rental_price_per_sqm` | `float64` | 97.11% | 57 | Range: [4.80 ➔ 20.00] | Mean: 12.98 |
| `cal_rental_price_index_base100` | `float64` | 97.11% | 80 | Range: [133.33 ➔ 377.36] | Mean: 286.94 |
| `cal_rental_price_change_1m` | `float64` | 97.11% | 65 | Range: [-0.06 ➔ 0.19] | Mean: 0.01 |
| `cal_rental_price_change_3m` | `float64` | 97.11% | 73 | Range: [-0.11 ➔ 0.24] | Mean: 0.01 |
| `cal_rental_price_change_12m` | `float64` | 97.11% | 82 | Range: [-0.09 ➔ 1.09] | Mean: 0.11 |
| `cal_rental_price_ma_3` | `float64` | 97.11% | 80 | Range: [4.73 ➔ 19.93] | Mean: 12.90 |
| `cal_rental_price_ma_12` | `float64` | 97.11% | 88 | Range: [4.69 ➔ 19.82] | Mean: 12.55 |
| `cal_rental_market_momentum_score` | `float64` | 97.11% | 90 | Range: [-0.04 ➔ 0.59] | Mean: 0.06 |
| `cal_rental_market_pressure_score` | `float64` | 97.11% | 90 | Range: [-0.05 ➔ 0.69] | Mean: 0.07 |
| `cal_rental_price_volatility_12m` | `float64` | 97.11% | 91 | Range: [0.07 ➔ 2.09] | Mean: 0.41 |
| `cal_rental_price_type_weight` | `float64` | 97.11% | 1 | Binary/Flag: {0.6: 2886} |
| `cal_rental_is_sale` | `float64` | 97.11% | 1 | Binary/Flag: {0.0: 2886} |
| `cal_rental_is_rental` | `float64` | 97.11% | 1 | Binary/Flag: {1.0: 2886} |
| `context_date_hpi` | `object` | 96.46% | 14 | Top: '2024-01-10': 2202 | '2023-01-10': 1058 |
| `hpi_year` | `float64` | 96.46% | 6 | Range: [2018.00 ➔ 2024.00] | Mean: 2023.54 |
| `hpi_hpi_value` | `float64` | 96.46% | 14 | Range: [132.34 ➔ 235.68] | Mean: 225.05 |
| `hpi_hpi_base100` | `float64` | 96.46% | 14 | Range: [125.24 ➔ 223.03] | Mean: 212.97 |
| `hpi_hpi_change_qoq` | `float64` | 96.46% | 14 | Range: [0.01 ➔ 0.04] | Mean: 0.02 |
| `hpi_hpi_change_yoy` | `float64` | 96.46% | 14 | Range: [0.07 ➔ 0.13] | Mean: 0.10 |
| `hpi_hpi_ma_4` | `float64` | 96.46% | 14 | Range: [129.03 ➔ 224.44] | Mean: 215.94 |
| `hpi_hpi_volatility_4` | `float64` | 96.46% | 14 | Range: [2.51 ➔ 10.06] | Mean: 8.34 |
| `hpi_is_total` | `float64` | 96.46% | 1 | Binary/Flag: {1.0: 3540} |
| `hpi_is_new` | `float64` | 96.46% | 1 | Binary/Flag: {0.0: 3540} |
| `hpi_is_existing` | `float64` | 96.46% | 1 | Binary/Flag: {0.0: 3540} |
| `context_date_macro` | `object` | 96.46% | 23 | Top: '2024-01-12': 2176 | '2023-01-12': 1058 |
| `macro_year` | `float64` | 96.46% | 6 | Range: [2018.00 ➔ 2024.00] | Mean: 2023.54 |
| `macro_month` | `float64` | 96.46% | 11 | Range: [2.00 ➔ 12.00] | Mean: 11.87 |
| `macro_value` | `float64` | 96.46% | 22 | Range: [0.57 ➔ 4.94] | Mean: 3.99 |
| `macro_base100` | `float64` | 96.46% | 22 | Range: [46.34 ➔ 401.63] | Mean: 324.19 |
| `macro_value_ma_3` | `float64` | 96.46% | 21 | Range: [0.58 ➔ 4.93] | Mean: 4.18 |
| `macro_value_ma_12` | `float64` | 96.46% | 22 | Range: [0.61 ➔ 4.80] | Mean: 4.30 |
| `macro_value_change_1m` | `float64` | 96.46% | 22 | Range: [-0.10 ➔ 0.47] | Mean: -0.05 |
| `macro_value_change_3m` | `float64` | 96.46% | 22 | Range: [-0.22 ➔ 1.27] | Mean: -0.07 |
| `macro_value_change_12m` | `float64` | 96.46% | 22 | Range: [-0.33 ➔ 5.68] | Mean: 0.22 |
| `macro_value_volatility_12m` | `float64` | 96.46% | 22 | Range: [0.03 ➔ 1.15] | Mean: 0.42 |
| `macro_shock_proxy` | `float64` | 96.46% | 23 | Range: [-0.27 ➔ 2.98] | Mean: 0.08 |
| `macro_demand_pressure_proxy` | `float64` | 96.46% | 22 | Range: [-5.68 ➔ 0.33] | Mean: -0.22 |
| `macro_affordability_score` | `float64` | 96.46% | 22 | Range: [0.11 ➔ 0.96] | Mean: 0.15 |
| `socio_pordata_average_value_of_buildings_euro_mean_mean_value_of_real_estate_negotiated_total` | `float64` | 3.54% | 2 | Binary/Flag: {53344.0: 96460, 108016.0: 4} |
| `socio_pordata_average_value_of_buildings_mortgaged_total` | `float64` | 3.54% | 2 | Binary/Flag: {89511.0: 96460, 135054.0: 4} |
| `socio_pordata_average_value_of_buildings_rural` | `float64` | 3.54% | 2 | Binary/Flag: {21507.0: 96460, 18037.0: 4} |
| `socio_pordata_average_value_of_buildings_urban` | `float64` | 3.54% | 2 | Binary/Flag: {62662.0: 96460, 135968.0: 4} |
| `socio_pordata_by_major_age_groups_0_14` | `float64` | 0.00% | 7 | Range: [1359648.00 ➔ 1685078.00] | Mean: 1673643.84 |
| `socio_pordata_by_major_age_groups_15_64` | `float64` | 0.00% | 7 | Range: [6604819.00 ➔ 6939317.00] | Mean: 6931394.52 |
| `socio_pordata_by_major_age_groups_65_or_more` | `float64` | 0.00% | 7 | Range: [1665503.00 ➔ 2589960.00] | Mean: 1697388.71 |
| `socio_pordata_by_major_age_groups_resident_population_total_and_by_major_age_groups_individual_major_age_groups_total` | `float64` | 0.00% | 7 | Range: [10289898.00 ➔ 10694681.00] | Mean: 10302427.04 |
| `socio_pordata_compensation_of_employees_compensation_of_employees_euro_thousands` | `float64` | 0.00% | 7 | Range: [61820370.00 ➔ 137966914.00] | Mean: 64336378.89 |
| `socio_pordata_new_dwellings_for_family_housing_by_dwelling_typology_2_bedroom` | `float64` | 0.00% | 7 | Range: [2286.00 ➔ 37722.00] | Mean: 36605.68 |
| `socio_pordata_new_dwellings_for_family_housing_by_dwelling_typology_3_bedroom` | `float64` | 0.00% | 7 | Range: [5577.00 ➔ 47333.00] | Mean: 46050.34 |
| `socio_pordata_new_dwellings_for_family_housing_by_dwelling_typology_4_bedroom_or_more` | `float64` | 0.00% | 7 | Range: [1868.00 ➔ 14300.00] | Mean: 13915.04 |
| `socio_pordata_new_dwellings_for_family_housing_by_dwelling_typology_completed_dwellings_in_new_constructions_for_family_housing_total_and_by_dwelling_typology_dwelling_dwelling_typology_total` | `float64` | 0.00% | 7 | Range: [10751.00 ➔ 112612.00] | Mean: 109485.88 |
| `socio_pordata_new_dwellings_for_family_housing_by_dwelling_typology_studio_or_1_bedroom` | `float64` | 0.00% | 7 | Range: [1020.00 ➔ 10234.00] | Mean: 9998.34 |
| `socio_pordata_new_dwellings_for_family_housing_by_dwelling_typology_undefined` | `float64` | 0.00% | 3 | Range: [0.00 ➔ 3023.00] | Mean: 2916.48 |
| `socio_pordata_permanent_immigrants_by_age_group_15_19` | `float64` | 98.70% | 5 | Range: [1974.00 ➔ 9513.00] | Mean: 8957.16 |
| `socio_pordata_permanent_immigrants_by_age_group_20_24` | `float64` | 98.70% | 5 | Range: [4594.00 ➔ 16340.00] | Mean: 15438.20 |
| `socio_pordata_permanent_immigrants_by_age_group_25_29` | `float64` | 98.70% | 5 | Range: [5703.00 ➔ 24297.00] | Mean: 22862.97 |
| `socio_pordata_permanent_immigrants_by_age_group_30_34` | `float64` | 98.70% | 5 | Range: [6466.00 ➔ 25495.00] | Mean: 24140.19 |
| `socio_pordata_permanent_immigrants_by_age_group_35_39` | `float64` | 98.70% | 5 | Range: [5242.00 ➔ 21258.00] | Mean: 20321.09 |
| `socio_pordata_permanent_immigrants_by_age_group_40_44` | `float64` | 98.70% | 5 | Range: [3060.00 ➔ 16842.00] | Mean: 16001.84 |
| `socio_pordata_permanent_immigrants_by_age_group_45_49` | `float64` | 98.70% | 5 | Range: [1673.00 ➔ 12232.00] | Mean: 11613.09 |
| `socio_pordata_permanent_immigrants_by_age_group_50_54` | `float64` | 98.70% | 5 | Range: [2266.00 ➔ 9229.00] | Mean: 8899.13 |
| `socio_pordata_permanent_immigrants_by_age_group_55_59` | `float64` | 98.70% | 5 | Range: [2411.00 ➔ 8386.00] | Mean: 8015.06 |
| `socio_pordata_permanent_immigrants_by_age_group_60_64` | `float64` | 98.70% | 5 | Range: [4863.00 ➔ 9603.00] | Mean: 9396.31 |
| `socio_pordata_permanent_immigrants_by_age_group_65_or_more` | `float64` | 98.70% | 5 | Range: [14293.00 ➔ 25545.00] | Mean: 15493.88 |
| `socio_pordata_permanent_immigrants_by_age_group_less_than_15` | `float64` | 98.70% | 5 | Range: [2812.00 ➔ 21590.00] | Mean: 20854.06 |
| `socio_pordata_permanent_immigrants_by_age_group_permanent_immigrants_total_and_by_age_group_individual_age_groups_total` | `float64` | 98.70% | 5 | Range: [55357.00 ➔ 189367.00] | Mean: 181992.97 |
| `socio_pordata_unemployment_rate_total_and_by_sex_percentage_females` | `float64` | 0.00% | 7 | Range: [4.90 ➔ 7.50] | Mean: 4.97 |
| `socio_pordata_unemployment_rate_total_and_by_sex_percentage_males` | `float64` | 0.00% | 7 | Range: [3.10 ➔ 6.90] | Mean: 3.20 |
| `socio_pordata_unemployment_rate_total_and_by_sex_percentage_unemployment_rate_total_and_by_sex_rate_sex_total` | `float64` | 0.00% | 7 | Range: [3.90 ➔ 7.20] | Mean: 3.99 |
| `al_muni_al_count` | `float64` | 93.64% | 1 | Binary/Flag: {11809.0: 6355} |
| `al_muni_al_risk` | `float64` | 93.64% | 1 | Binary/Flag: {0.1267610656531528: 6355} |
| `listing_date_parsed` | `object` | 3.56% | 1 | Top: '2000-01-01': 96444 |
| `merge_date_parsed` | `object` | 3.56% | 1 | Top: '2000-01-01': 96444 |


## 📁 System Component: `Aura -Dataset -Second Version`

### 📄 Dataset: **aura__fused_dataset_Version 2.csv**
- **Sample Analyzed:** 100,000 rows
- **Total Features:** 174
| Feature Name | Data Type | Missing (%) | Unique Values | Distribution / Top Values |
|---|---|---|---|---|
| `grid_id_250m` | `object` | 0.00% | 7,209 | Top: '-122_560': 14 | '-100_-1007': 14 |
| `municipality` | `object` | 0.00% | 13 | Top: 'Gondomar': 21955 | 'Coimbra': 21266 |
| `year` | `int64` | 0.00% | 7 | Range: [2019.00 ➔ 2025.00] | Mean: 2022.00 |
| `quarter` | `int64` | 0.00% | 2 | Binary/Flag: {3: 50091, 1: 49909} |
| `buildings_in_grid_mean` | `float64` | 0.00% | 138 | Range: [1.00 ➔ 326.00] | Mean: 8.93 |
| `buildings_in_grid_sum` | `int64` | 0.00% | 138 | Range: [1.00 ➔ 106276.00] | Mean: 417.56 |
| `buildings_in_grid_max` | `int64` | 0.00% | 138 | Range: [1.00 ➔ 326.00] | Mean: 8.93 |
| `local_density_score_mean` | `float64` | 0.00% | 6,452 | Range: [0.00 ➔ 4.12] | Mean: 0.06 |
| `local_density_score_median` | `float64` | 0.00% | 6,452 | Range: [0.00 ➔ 4.12] | Mean: 0.06 |
| `local_density_score_min` | `float64` | 0.00% | 6,452 | Range: [0.00 ➔ 4.12] | Mean: 0.06 |
| `local_density_score_max` | `float64` | 0.00% | 6,452 | Range: [0.00 ➔ 4.12] | Mean: 0.06 |
| `local_density_score_q10` | `float64` | 0.00% | 6,452 | Range: [0.00 ➔ 4.12] | Mean: 0.06 |
| `local_density_score_q90` | `float64` | 0.00% | 6,452 | Range: [0.00 ➔ 4.12] | Mean: 0.06 |
| `log_footprint_area_mean` | `float64` | 0.00% | 7,002 | Range: [1.91 ➔ 7.69] | Mean: 5.25 |
| `log_footprint_area_std` | `float64` | 0.00% | 5,019 | Range: [0.00 ➔ 3.56] | Mean: 0.71 |
| `log_footprint_area_median` | `float64` | 0.00% | 6,965 | Range: [1.91 ➔ 7.69] | Mean: 5.26 |
| `log_footprint_area_min` | `float64` | 0.00% | 6,885 | Range: [1.91 ➔ 7.69] | Mean: 4.57 |
| `log_footprint_area_max` | `float64` | 0.00% | 6,347 | Range: [1.91 ➔ 7.69] | Mean: 5.91 |
| `log_footprint_area_q10` | `float64` | 0.00% | 6,996 | Range: [1.91 ➔ 7.69] | Mean: 4.78 |
| `log_footprint_area_q90` | `float64` | 0.00% | 6,868 | Range: [1.91 ➔ 7.69] | Mean: 5.70 |
| `compactness_mean` | `float64` | 0.00% | 7,127 | Range: [0.28 ➔ 0.80] | Mean: 0.67 |
| `compactness_std` | `float64` | 0.00% | 5,058 | Range: [0.00 ➔ 0.37] | Mean: 0.09 |
| `compactness_median` | `float64` | 0.00% | 7,095 | Range: [0.28 ➔ 0.80] | Mean: 0.68 |
| `compactness_min` | `float64` | 0.00% | 6,715 | Range: [0.28 ➔ 0.80] | Mean: 0.56 |
| `compactness_max` | `float64` | 0.00% | 6,700 | Range: [0.28 ➔ 0.80] | Mean: 0.73 |
| `compactness_q10` | `float64` | 0.00% | 7,097 | Range: [0.28 ➔ 0.80] | Mean: 0.60 |
| `compactness_q90` | `float64` | 0.00% | 7,072 | Range: [0.28 ➔ 0.80] | Mean: 0.72 |
| `elongation_ratio_mean` | `float64` | 0.00% | 7,168 | Range: [1.00 ➔ 3.14] | Mean: 1.33 |
| `elongation_ratio_std` | `float64` | 0.00% | 5,061 | Range: [0.00 ➔ 1.50] | Mean: 0.26 |
| `elongation_ratio_median` | `float64` | 0.00% | 7,161 | Range: [1.00 ➔ 3.14] | Mean: 1.29 |
| `elongation_ratio_min` | `float64` | 0.00% | 6,744 | Range: [1.00 ➔ 3.14] | Mean: 1.17 |
| `elongation_ratio_max` | `float64` | 0.00% | 6,788 | Range: [1.00 ➔ 3.14] | Mean: 1.67 |
| `elongation_ratio_q10` | `float64` | 0.00% | 7,155 | Range: [1.00 ➔ 3.14] | Mean: 1.19 |
| `elongation_ratio_q90` | `float64` | 0.00% | 7,132 | Range: [1.00 ➔ 3.14] | Mean: 1.51 |
| `coverage_ratio_mean` | `float64` | 0.00% | 7,157 | Range: [0.29 ➔ 0.98] | Mean: 0.60 |
| `coverage_ratio_std` | `float64` | 0.00% | 5,057 | Range: [0.00 ➔ 0.49] | Mean: 0.10 |
| `coverage_ratio_median` | `float64` | 0.00% | 7,145 | Range: [0.29 ➔ 0.98] | Mean: 0.59 |
| `coverage_ratio_min` | `float64` | 0.00% | 6,745 | Range: [0.29 ➔ 0.98] | Mean: 0.50 |
| `coverage_ratio_max` | `float64` | 0.00% | 6,814 | Range: [0.29 ➔ 0.98] | Mean: 0.70 |
| `coverage_ratio_q10` | `float64` | 0.00% | 7,126 | Range: [0.29 ➔ 0.98] | Mean: 0.53 |
| `coverage_ratio_q90` | `float64` | 0.00% | 7,121 | Range: [0.29 ➔ 0.98] | Mean: 0.67 |
| `mean_compactness_mean` | `float64` | 0.00% | 6,392 | Range: [0.49 ➔ 0.78] | Mean: 0.67 |
| `mean_coverage_ratio_mean` | `float64` | 0.00% | 6,668 | Range: [0.41 ➔ 0.89] | Mean: 0.60 |
| `morphology_score_mean` | `float64` | 0.00% | 6,554 | Range: [0.22 ➔ 0.64] | Mean: 0.40 |
| `energy_score_clean_mean` | `float64` | 0.00% | 7,050 | Range: [0.18 ➔ 0.73] | Mean: 0.23 |
| `energy_score_clean_std` | `float64` | 0.00% | 5,054 | Range: [0.00 ➔ 0.12] | Mean: 0.03 |
| `energy_score_clean_median` | `float64` | 0.00% | 7,007 | Range: [0.18 ➔ 0.73] | Mean: 0.23 |
| `energy_score_clean_min` | `float64` | 0.00% | 6,517 | Range: [0.18 ➔ 0.70] | Mean: 0.21 |
| `energy_score_clean_max` | `float64` | 0.00% | 7,050 | Range: [0.18 ➔ 0.91] | Mean: 0.26 |
| `energy_score_clean_q10` | `float64` | 0.00% | 6,929 | Range: [0.18 ➔ 0.70] | Mean: 0.22 |
| `energy_score_clean_q90` | `float64` | 0.00% | 7,050 | Range: [0.18 ➔ 0.76] | Mean: 0.25 |
| `renovation_score_clean_mean` | `float64` | 0.00% | 7,117 | Range: [0.09 ➔ 0.76] | Mean: 0.44 |
| `renovation_score_clean_std` | `float64` | 0.00% | 5,055 | Range: [0.00 ➔ 0.47] | Mean: 0.11 |
| `renovation_score_clean_median` | `float64` | 0.00% | 7,103 | Range: [0.09 ➔ 0.76] | Mean: 0.44 |
| `renovation_score_clean_min` | `float64` | 0.00% | 6,844 | Range: [0.09 ➔ 0.76] | Mean: 0.34 |
| `renovation_score_clean_max` | `float64` | 0.00% | 6,642 | Range: [0.09 ➔ 0.76] | Mean: 0.54 |
| `renovation_score_clean_q10` | `float64` | 0.00% | 7,099 | Range: [0.09 ➔ 0.76] | Mean: 0.37 |
| `renovation_score_clean_q90` | `float64` | 0.00% | 7,067 | Range: [0.09 ➔ 0.76] | Mean: 0.51 |
| `sustainability_index_mean` | `float64` | 0.00% | 7,141 | Range: [0.03 ➔ 0.29] | Mean: 0.10 |
| `sustainability_index_std` | `float64` | 0.00% | 5,061 | Range: [0.00 ➔ 0.16] | Mean: 0.03 |
| `sustainability_index_median` | `float64` | 0.00% | 7,133 | Range: [0.03 ➔ 0.31] | Mean: 0.10 |
| `sustainability_index_min` | `float64` | 0.00% | 6,775 | Range: [0.03 ➔ 0.29] | Mean: 0.08 |
| `sustainability_index_max` | `float64` | 0.00% | 7,117 | Range: [0.03 ➔ 0.35] | Mean: 0.14 |
| `sustainability_index_q10` | `float64` | 0.00% | 7,107 | Range: [0.03 ➔ 0.29] | Mean: 0.08 |
| `sustainability_index_q90` | `float64` | 0.00% | 7,141 | Range: [0.03 ➔ 0.35] | Mean: 0.13 |
| `centroid_lat_mean` | `float64` | 0.00% | 6,768 | Range: [37.08 ➔ 41.92] | Mean: 40.13 |
| `centroid_lon_mean` | `float64` | 0.00% | 7,209 | Range: [-8.50 ➔ -8.16] | Mean: -8.45 |
| `density_index` | `float64` | 0.00% | 138 | Range: [1.00 ➔ 326.00] | Mean: 8.93 |
| `urban_pressure_score` | `float64` | 0.00% | 7,190 | Range: [0.00 ➔ 2.28] | Mean: 0.04 |
| `urban_dominance` | `float64` | 0.00% | 138 | Range: [1.00 ➔ 1.00] | Mean: 1.00 |
| `esg_index` | `float64` | 0.00% | 7,176 | Range: [0.10 ➔ 0.48] | Mean: 0.17 |
| `esg_inequality` | `float64` | 0.00% | 4,940 | Range: [0.00 ➔ 0.20] | Mean: 0.03 |
| `renovation_hotspot` | `float64` | 0.00% | 7,185 | Range: [0.06 ➔ 0.60] | Mean: 0.39 |
| `morphology_stability` | `float64` | 0.00% | 5,019 | Range: [0.28 ➔ 100000.00] | Mean: 1040.92 |
| `urban_attractiveness_score` | `float64` | 0.00% | 7,179 | Range: [0.03 ➔ 58.96] | Mean: 0.71 |
| `density_strength` | `float64` | 0.00% | 6,458 | Range: [0.00 ➔ 1261.34] | Mean: 3.26 |
| `dist_nearest_poi` | `float64` | 0.00% | 7,198 | Range: [0.00 ➔ 17388.87] | Mean: 1486.05 |
| `dist_multipolygon` | `float64` | 0.00% | 7,209 | Range: [44.00 ➔ 52634.46] | Mean: 17429.63 |
| `poi_density_1km` | `int64` | 0.00% | 44 | Range: [0.00 ➔ 45.00] | Mean: 3.77 |
| `density_multipolygon_1km` | `int64` | 0.00% | 2 | Binary/Flag: {0: 98866, 1: 1134} |
| `nearest_poi_score` | `float64` | 0.00% | 7,198 | Range: [0.00 ➔ 1.00] | Mean: 0.01 |
| `multipolygon_score` | `float64` | 0.00% | 7,209 | Range: [0.00 ➔ 0.02] | Mean: 0.00 |
| `accessibility_score` | `float64` | 0.00% | 7,209 | Range: [0.00 ➔ 0.50] | Mean: 0.00 |
| `price_per_m2` | `float64` | 0.00% | 174 | Range: [1115.00 ➔ 4346.00] | Mean: 1869.09 |
| `price_growth` | `float64` | 0.00% | 176 | Range: [-0.14 ➔ 0.12] | Mean: -0.03 |
| `price_trend` | `float64` | 0.00% | 161 | Range: [736.67 ➔ 4084.67] | Mean: 1775.92 |
| `price_volatility` | `float64` | 0.00% | 150 | Range: [11.82 ➔ 364.60] | Mean: 85.82 |
| `hpi_value` | `float64` | 0.00% | 14 | Range: [137.14 ➔ 269.35] | Mean: 190.09 |
| `hpi_base100` | `float64` | 0.00% | 14 | Range: [129.78 ➔ 254.90] | Mean: 179.89 |
| `hpi_change_qoq` | `float64` | 0.00% | 14 | Range: [-0.00 ➔ 0.05] | Mean: 0.03 |
| `hpi_change_yoy` | `float64` | 0.00% | 14 | Range: [0.07 ➔ 0.18] | Mean: 0.11 |
| `hpi_ma_4` | `float64` | 0.00% | 14 | Range: [131.92 ➔ 252.72] | Mean: 182.70 |
| `hpi_volatility_4` | `float64` | 0.00% | 14 | Range: [3.43 ➔ 14.56] | Mean: 6.35 |
| `price_sqm_proxy` | `float64` | 0.00% | 14 | Range: [137.14 ➔ 269.35] | Mean: 190.09 |
| `price_dispersion_proxy` | `float64` | 0.00% | 14 | Range: [3.43 ➔ 14.56] | Mean: 6.35 |
| `price_trend_strength` | `float64` | 0.00% | 14 | Range: [-16.63 ➔ -2.19] | Mean: -7.39 |
| `liquidity_proxy` | `float64` | 0.00% | 14 | Range: [-0.02 ➔ 0.59] | Mean: 0.20 |
| `liquidity_growth` | `float64` | 0.00% | 14 | Range: [-1.20 ➔ 1.77] | Mean: 0.22 |
| `market_speed_proxy` | `float64` | 0.00% | 14 | Range: [-0.00 ➔ 0.01] | Mean: 0.00 |
| `market_acceleration` | `float64` | 0.00% | 14 | Range: [-0.14 ➔ -0.04] | Mean: -0.08 |
| `market_pressure_behavior` | `float64` | 0.00% | 14 | Range: [-0.02 ➔ 0.59] | Mean: 0.20 |
| `trend_momentum_behavior` | `float64` | 0.00% | 14 | Range: [2.49 ➔ 10.12] | Mean: 4.67 |
| `value` | `float64` | 0.00% | 14 | Range: [0.61 ➔ 4.83] | Mean: 2.27 |
| `base100` | `float64` | 0.00% | 14 | Range: [49.32 ➔ 392.41] | Mean: 184.34 |
| `value_ma_3` | `float64` | 0.00% | 14 | Range: [0.58 ➔ 4.88] | Mean: 2.26 |
| `value_ma_12` | `float64` | 0.00% | 14 | Range: [0.60 ➔ 4.78] | Mean: 2.17 |
| `value_change_1m` | `float64` | 0.00% | 14 | Range: [-0.09 ➔ 0.19] | Mean: 0.01 |
| `value_change_3m` | `float64` | 0.00% | 14 | Range: [-0.15 ➔ 0.90] | Mean: 0.05 |
| `value_change_12m` | `float64` | 0.00% | 13 | Range: [-0.38 ➔ 5.26] | Mean: 0.49 |
| `value_volatility_12m` | `float64` | 0.00% | 14 | Range: [0.01 ➔ 1.10] | Mean: 0.32 |
| `shock_proxy` | `float64` | 0.00% | 14 | Range: [-0.22 ➔ 2.77] | Mean: 0.29 |
| `demand_pressure_proxy` | `float64` | 0.00% | 13 | Range: [-5.26 ➔ 0.38] | Mean: -0.49 |
| `affordability_score` | `float64` | 0.00% | 14 | Range: [0.11 ➔ 0.91] | Mean: 0.44 |
| `trend_encoded` | `float64` | 0.00% | 5 | Range: [0.00 ➔ 2.00] | Mean: 1.22 |
| `rate_acceleration` | `float64` | 0.00% | 14 | Range: [-0.71 ➔ 0.11] | Mean: -0.04 |
| `macro_stress_score` | `float64` | 0.00% | 14 | Range: [0.01 ➔ 4.20] | Mean: 1.05 |
| `tightening_intensity` | `float64` | 0.00% | 14 | Range: [-0.21 ➔ 5.80] | Mean: 0.54 |
| `affordability_pressure` | `float64` | 0.00% | 14 | Range: [0.67 ➔ 42.36] | Mean: 14.09 |
| `log_interest_rate` | `float64` | 0.00% | 14 | Range: [0.47 ➔ 1.76] | Mean: 1.06 |
| `trend_label` | `object` | 0.00% | 3 | Top: 'tightening': 57299 | 'expansion': 28283 |
| `macro_regime` | `object` | 0.00% | 3 | Top: 'easing': 43250 | 'tightening': 35491 |
| `population_0_14` | `float64` | 0.00% | 6 | Range: [1359648.00 ➔ 1399628.00] | Mean: 1370617.38 |
| `population_15_64` | `float64` | 0.00% | 6 | Range: [6604819.00 ➔ 6743093.00] | Mean: 6662309.24 |
| `population_65_or_more` | `float64` | 0.00% | 6 | Range: [2327150.00 ➔ 2589960.00] | Mean: 2479072.67 |
| `economic_power_index` | `float64` | 0.00% | 7 | Range: [18.39 ➔ 18.81] | Mean: 18.57 |
| `unemployment_rate` | `float64` | 0.00% | 7 | Range: [6.00 ➔ 7.00] | Mean: 6.47 |
| `labor_stress` | `float64` | 0.00% | 7 | Range: [40399982.80 ➔ 46314044.00] | Mean: 43096751.23 |
| `housing_supply_total` | `float64` | 0.00% | 6 | Range: [12954.00 ➔ 25311.00] | Mean: 20586.81 |
| `supply_pressure` | `float64` | 0.00% | 6 | Range: [0.00 ➔ 0.00] | Mean: 0.00 |
| `construction_intensity` | `float64` | 0.00% | 6 | Range: [0.01 ➔ 0.01] | Mean: 0.01 |
| `immigration_total` | `float64` | 0.00% | 5 | Range: [83654.00 ➔ 189367.00] | Mean: 144494.49 |
| `immigration_pressure` | `float64` | 0.00% | 6 | Range: [0.01 ➔ 0.02] | Mean: 0.01 |
| `macro_demand_index` | `float64` | 0.00% | 7 | Range: [11.40 ➔ 12.83] | Mean: 12.11 |
| `housing_imbalance` | `float64` | 0.00% | 6 | Range: [0.01 ➔ 0.02] | Mean: 0.01 |
| `socio_momentum` | `float64` | 0.00% | 7 | Range: [-0.52 ➔ 1.41] | Mean: 0.47 |
| `aging_ratio` | `float64` | 0.00% | 6 | Range: [0.35 ➔ 0.38] | Mean: 0.37 |
| `youth_ratio` | `float64` | 0.00% | 6 | Range: [0.20 ➔ 0.21] | Mean: 0.21 |
| `price_per_sqm` | `float64` | 0.00% | 13 | Range: [677.16 ➔ 970.63] | Mean: 816.76 |
| `price_index_base100` | `float64` | 0.00% | 13 | Range: [141.35 ➔ 233.54] | Mean: 178.46 |
| `price_change_1m` | `float64` | 0.00% | 13 | Range: [0.00 ➔ 0.02] | Mean: 0.01 |
| `price_change_3m` | `float64` | 0.00% | 13 | Range: [0.00 ➔ 0.06] | Mean: 0.03 |
| `price_change_12m` | `float64` | 0.00% | 13 | Range: [0.04 ➔ 0.20] | Mean: 0.10 |
| `price_ma_3` | `float64` | 0.00% | 13 | Range: [673.06 ➔ 961.66] | Mean: 811.66 |
| `price_ma_12` | `float64` | 0.00% | 13 | Range: [653.48 ➔ 933.39] | Mean: 787.10 |
| `market_momentum_score` | `float64` | 0.00% | 13 | Range: [0.03 ➔ 0.13] | Mean: 0.06 |
| `market_pressure_score` | `float64` | 0.00% | 13 | Range: [0.03 ➔ 0.14] | Mean: 0.07 |
| `price_volatility_12m` | `float64` | 0.00% | 13 | Range: [15.96 ➔ 34.11] | Mean: 24.87 |
| `price_type_weight` | `float64` | 0.00% | 9 | Range: [0.80 ➔ 0.84] | Mean: 0.82 |
| `is_sale` | `float64` | 0.00% | 9 | Range: [0.51 ➔ 0.60] | Mean: 0.56 |
| `is_rental` | `float64` | 0.00% | 9 | Range: [0.40 ➔ 0.49] | Mean: 0.44 |
| `log_price_per_sqm` | `float64` | 0.00% | 13 | Range: [4.81 ➔ 5.12] | Mean: 4.98 |
| `momentum_volatility_interaction` | `float64` | 0.00% | 13 | Range: [0.52 ➔ 3.79] | Mean: 1.66 |
| `trend_strength` | `float64` | 0.00% | 13 | Range: [12.87 ➔ 39.97] | Mean: 24.43 |
| `price_acceleration` | `float64` | 0.00% | 13 | Range: [-0.05 ➔ -0.00] | Mean: -0.02 |
| `price_type_weight_norm` | `float64` | 0.00% | 9 | Range: [0.80 ➔ 0.84] | Mean: 0.82 |
| `region_encoded` | `float64` | 0.00% | 11 | Range: [10.15 ➔ 10.67] | Mean: 10.38 |
| `price_type_encoded` | `float64` | 0.00% | 9 | Range: [0.51 ➔ 0.60] | Mean: 0.56 |
| `beds` | `float64` | 0.00% | 14 | Range: [2.89 ➔ 6.50] | Mean: 3.85 |
| `guests` | `float64` | 0.00% | 14 | Range: [4.00 ➔ 9.75] | Mean: 6.01 |
| `tourism_capacity_score` | `float64` | 0.00% | 14 | Range: [3.45 ➔ 7.96] | Mean: 4.80 |
| `regulatory_pressure_score` | `float64` | 0.00% | 14 | Range: [0.00 ➔ 0.31] | Mean: 0.22 |
| `investor_risk_score` | `float64` | 0.00% | 14 | Range: [0.00 ➔ 0.14] | Mean: 0.10 |
| `accommodation_type_enc` | `float64` | 0.00% | 14 | Range: [1.00 ➔ 4.67] | Mean: 1.81 |
| `owner_type_enc` | `float64` | 0.00% | 13 | Range: [0.35 ➔ 1.00] | Mean: 0.59 |
| `district_enc` | `float64` | 0.00% | 14 | Range: [5.00 ➔ 15.89] | Mean: 10.68 |
| `tourism_zone_label_enc` | `float64` | 0.00% | 14 | Range: [0.76 ➔ 2.00] | Mean: 1.25 |
| `risk_band_enc` | `float64` | 0.00% | 12 | Range: [0.79 ➔ 1.00] | Mean: 0.93 |
| `tourism_pressure_index` | `float64` | 0.00% | 14 | Range: [40741.05 ➔ 94029.16] | Mean: 56657.76 |
| `regulatory_risk_index` | `float64` | 0.00% | 14 | Range: [0.00 ➔ 0.10] | Mean: 0.06 |
| `seller_urgency_score` | `float64` | 0.00% | 14 | Range: [40741.05 ➔ 94029.20] | Mean: 56657.82 |
| `occupancy_ratio` | `float64` | 0.00% | 14 | Range: [1.33 ➔ 1.88] | Mean: 1.73 |
| `demand_pressure_score` | `float64` | 0.00% | 14 | Range: [4.60 ➔ 12.45] | Mean: 7.84 |
| `log_tourism_pressure` | `float64` | 0.00% | 14 | Range: [10.58 ➔ 11.16] | Mean: 10.75 |
| `log_demand_pressure` | `float64` | 0.00% | 14 | Range: [1.72 ➔ 2.42] | Mean: 2.04 |


## 📁 System Component: `Aura -Datasets -Final Version\Dataset A Final`

### 📄 Dataset: **AURA_SPATIAL_MASTER_V6_FINAL.csv**
- **Sample Analyzed:** 100,000 rows
- **Total Features:** 41
| Feature Name | Data Type | Missing (%) | Unique Values | Distribution / Top Values |
|---|---|---|---|---|
| `osm_id` | `int64` | 0.00% | 100,000 | Range: [33527519.00 ➔ 1480853669.00] | Mean: 705522834.86 |
| `centroid_lon` | `float64` | 0.00% | 95,495 | Range: [-31.26 ➔ -6.22] | Mean: -10.18 |
| `centroid_lat` | `float64` | 0.00% | 78,563 | Range: [32.63 ➔ 42.16] | Mean: 39.21 |
| `footprint_area_m2` | `float64` | 0.00% | 99,855 | Range: [0.25 ➔ 80140.01] | Mean: 216.59 |
| `footprint_perimeter_m` | `float64` | 0.00% | 99,750 | Range: [2.06 ➔ 1789.62] | Mean: 50.44 |
| `compactness` | `float64` | 0.00% | 97,549 | Range: [0.02 ➔ 1.00] | Mean: 0.68 |
| `elongation_ratio` | `float64` | 0.00% | 98,780 | Range: [1.00 ➔ 29.54] | Mean: 1.33 |
| `coverage_ratio` | `float64` | 0.00% | 99,381 | Range: [0.06 ➔ 1.00] | Mean: 0.61 |
| `area_to_perimeter_ratio` | `float64` | 0.00% | 99,769 | Range: [0.11 ➔ 60.60] | Mean: 2.57 |
| `grid_id_250m` | `object` | 0.00% | 17,198 | Top: '-144_450': 260 | '-33_-611': 198 |
| `buildings_in_grid` | `int64` | 0.00% | 353 | Range: [1.00 ➔ 721.00] | Mean: 88.64 |
| `local_density_score` | `float64` | 0.00% | 17,194 | Range: [0.00 ➔ 24.63] | Mean: 1.16 |
| `esg_proxy_energy_score` | `float64` | 0.00% | 99,575 | Range: [0.17 ➔ 5.24] | Mean: 0.48 |
| `esg_proxy_energy_score_norm` | `float64` | 0.00% | 99,797 | Range: [0.00 ➔ 0.99] | Mean: 0.06 |
| `green_premium_proxy` | `object` | 0.00% | 4 | Top: 'very_low': 98055 | 'low': 1680 |
| `renovation_potential_proxy` | `float64` | 0.00% | 99,664 | Range: [0.01 ➔ 0.98] | Mean: 0.36 |
| `esg_risk_label` | `object` | 0.00% | 4 | Top: 'high_risk': 96425 | 'elevated_risk': 3243 |
| `building_class` | `object` | 0.00% | 90 | Top: 'yes': 79951 | 'house': 10741 |
| `sustainability_index_mean` | `float64` | 0.00% | 17,109 | Range: [0.03 ➔ 0.34] | Mean: 0.13 |
| `sustainability_index_std` | `float64` | 0.00% | 16,591 | Range: [0.00 ➔ 0.16] | Mean: 0.05 |
| `sustainability_index_median` | `float64` | 0.00% | 17,078 | Range: [0.03 ➔ 0.35] | Mean: 0.12 |
| `sustainability_index_min` | `float64` | 0.00% | 14,458 | Range: [0.03 ➔ 0.32] | Mean: 0.05 |
| `sustainability_index_max` | `float64` | 0.00% | 16,417 | Range: [0.03 ➔ 0.35] | Mean: 0.24 |
| `sustainability_index_q10` | `float64` | 0.00% | 16,895 | Range: [0.03 ➔ 0.32] | Mean: 0.07 |
| `sustainability_index_q90` | `float64` | 0.00% | 16,996 | Range: [0.03 ➔ 0.35] | Mean: 0.18 |
| `density_index` | `float64` | 0.00% | 353 | Range: [1.00 ➔ 721.00] | Mean: 88.64 |
| `urban_pressure_score` | `float64` | 0.00% | 17,166 | Range: [0.00 ➔ 5.29] | Mean: 0.69 |
| `urban_dominance` | `float64` | 0.00% | 26 | Range: [1.00 ➔ 1.00] | Mean: 1.00 |
| `esg_index` | `float64` | 0.00% | 17,153 | Range: [0.10 ➔ 0.66] | Mean: 0.25 |
| `esg_inequality` | `float64` | 0.00% | 15,505 | Range: [0.00 ➔ 0.25] | Mean: 0.06 |
| `renovation_hotspot` | `float64` | 0.00% | 17,162 | Range: [0.01 ➔ 0.60] | Mean: 0.33 |
| `morphology_stability` | `float64` | 0.00% | 16,451 | Range: [0.26 ➔ 100000.00] | Mean: 308.85 |
| `urban_attractiveness_score` | `float64` | 0.00% | 17,170 | Range: [0.03 ➔ 197.89] | Mean: 13.46 |
| `density_strength` | `float64` | 0.00% | 16,457 | Range: [0.00 ➔ 2889.33] | Mean: 243.47 |
| `dist_nearest_poi` | `float64` | 0.00% | 17,192 | Range: [0.00 ➔ 86249.10] | Mean: 1912.84 |
| `dist_multipolygon` | `float64` | 0.00% | 17,195 | Range: [3.50 ➔ 178021.02] | Mean: 18295.00 |
| `poi_density_1km` | `int64` | 0.00% | 69 | Range: [0.00 ➔ 77.00] | Mean: 10.25 |
| `density_multipolygon_1km` | `int64` | 0.00% | 8 | Range: [0.00 ➔ 8.00] | Mean: 0.07 |
| `nearest_poi_score` | `float64` | 0.00% | 17,193 | Range: [0.00 ➔ 1.00] | Mean: 0.01 |
| `multipolygon_score` | `float64` | 0.00% | 17,193 | Range: [0.00 ➔ 0.22] | Mean: 0.00 |
| `accessibility_score` | `float64` | 0.00% | 17,193 | Range: [0.00 ➔ 0.50] | Mean: 0.00 |


## 📁 System Component: `Aura -Datasets -Final Version\Dataset B Final`

### 📄 Dataset: **AURA_MARKET_MASTER_V2.csv**
- **Sample Analyzed:** 40 rows
- **Total Features:** 104
| Feature Name | Data Type | Missing (%) | Unique Values | Distribution / Top Values |
|---|---|---|---|---|
| `year` | `int64` | 0.00% | 10 | Range: [2015.00 ➔ 2024.00] | Mean: 2019.50 |
| `quarter` | `int64` | 0.00% | 4 | Range: [1.00 ➔ 4.00] | Mean: 2.50 |
| `period_str` | `object` | 0.00% | 40 | Likely Primary Key / Unique ID |
| `aveiro_rental` | `float64` | 0.00% | 37 | Range: [3.70 ➔ 9.70] | Mean: 6.19 |
| `aveiro_sale` | `float64` | 0.00% | 40 | Range: [782.67 ➔ 1772.67] | Mean: 1183.32 |
| `azores_sale` | `float64` | 0.00% | 40 | Range: [835.58 ➔ 1441.33] | Mean: 1007.35 |
| `beja_sale` | `float64` | 0.00% | 38 | Range: [763.67 ➔ 1194.00] | Mean: 857.13 |
| `braga_sale` | `float64` | 0.00% | 39 | Range: [729.67 ➔ 1672.33] | Mean: 1068.45 |
| `braganca_sale` | `float64` | 0.00% | 38 | Range: [662.33 ➔ 927.33] | Mean: 754.77 |
| `castelo-branco_sale` | `float64` | 0.00% | 37 | Range: [659.67 ➔ 877.67] | Mean: 720.62 |
| `coimbra_sale` | `float64` | 0.00% | 40 | Range: [941.33 ➔ 1494.00] | Mean: 1143.55 |
| `evora_sale` | `float64` | 0.00% | 39 | Range: [822.33 ➔ 1447.00] | Mean: 999.81 |
| `faro_rental` | `float64` | 0.00% | 40 | Range: [4.80 ➔ 14.53] | Mean: 9.17 |
| `faro_sale` | `float64` | 0.00% | 40 | Range: [1397.33 ➔ 3536.00] | Mean: 2274.54 |
| `guarda_sale` | `float64` | 0.00% | 39 | Range: [783.00 ➔ 1712.67] | Mean: 1148.38 |
| `leiria_rental` | `float64` | 0.00% | 37 | Range: [3.63 ➔ 9.70] | Mean: 5.85 |
| `leiria_sale` | `float64` | 0.00% | 39 | Range: [783.00 ➔ 1712.67] | Mean: 1148.38 |
| `lisboa_rental` | `float64` | 0.00% | 38 | Range: [5.97 ➔ 19.93] | Mean: 13.30 |
| `lisboa_sale` | `float64` | 0.00% | 40 | Range: [1336.33 ➔ 4218.67] | Mean: 2978.67 |
| `madeira_sale` | `float64` | 0.00% | 40 | Range: [1144.33 ➔ 2891.17] | Mean: 1621.24 |
| `portalegre_sale` | `float64` | 0.00% | 40 | Range: [592.67 ➔ 798.33] | Mean: 678.34 |
| `porto_rental` | `float64` | 0.00% | 35 | Range: [4.80 ➔ 15.57] | Mean: 9.63 |
| `porto_sale` | `float64` | 0.00% | 40 | Range: [968.33 ➔ 2857.33] | Mean: 1823.04 |
| `portugal_rental` | `float64` | 0.00% | 37 | Range: [4.77 ➔ 16.30] | Mean: 10.55 |
| `portugal_sale` | `float64` | 0.00% | 40 | Range: [1038.33 ➔ 2781.00] | Mean: 1902.48 |
| `santarem_rental` | `float64` | 0.00% | 34 | Range: [3.40 ➔ 8.13] | Mean: 4.97 |
| `santarem_sale` | `float64` | 0.00% | 40 | Range: [701.67 ➔ 1257.00] | Mean: 847.79 |
| `setubal_rental` | `float64` | 0.00% | 37 | Range: [4.50 ➔ 13.33] | Mean: 8.11 |
| `setubal_sale` | `float64` | 0.00% | 40 | Range: [977.33 ➔ 2661.00] | Mean: 1628.96 |
| `viana-do-castelo_sale` | `float64` | 0.00% | 37 | Range: [897.67 ➔ 1473.67] | Mean: 1076.37 |
| `vila-real_sale` | `float64` | 0.00% | 40 | Range: [738.67 ➔ 1045.33] | Mean: 844.36 |
| `viseu_sale` | `float64` | 0.00% | 40 | Range: [721.33 ➔ 1128.00] | Mean: 838.12 |
| `braga_rental` | `float64` | 0.00% | 37 | Range: [3.47 ➔ 9.53] | Mean: 5.95 |
| `castelo-branco_rental` | `float64` | 0.00% | 31 | Range: [3.10 ➔ 7.13] | Mean: 4.84 |
| `coimbra_rental` | `float64` | 0.00% | 37 | Range: [4.43 ➔ 10.63] | Mean: 6.60 |
| `madeira_rental` | `float64` | 0.00% | 36 | Range: [4.97 ➔ 14.90] | Mean: 8.51 |
| `viana-do-castelo_rental` | `float64` | 0.00% | 32 | Range: [3.63 ➔ 8.90] | Mean: 5.54 |
| `vila-real_rental` | `float64` | 10.00% | 34 | Range: [3.23 ➔ 7.43] | Mean: 4.63 |
| `viseu_rental` | `float64` | 0.00% | 36 | Range: [3.10 ➔ 7.27] | Mean: 4.60 |
| `beja_rental` | `float64` | 57.50% | 14 | Range: [3.90 ➔ 9.70] | Mean: 6.17 |
| `guarda_rental` | `float64` | 92.50% | 3 | Range: [2.80 ➔ 2.95] | Mean: 2.87 |
| `evora_rental` | `float64` | 17.50% | 31 | Range: [4.50 ➔ 10.77] | Mean: 7.19 |
| `portalegre_rental` | `float64` | 57.50% | 16 | Range: [3.10 ➔ 6.93] | Mean: 4.74 |
| `azores_rental` | `float64` | 55.00% | 17 | Range: [6.20 ➔ 9.90] | Mean: 7.50 |
| `period` | `object` | 0.00% | 40 | Likely Primary Key / Unique ID |
| `transaction_value_thousands` | `int64` | 0.00% | 40 | Range: [2509888.00 ➔ 10173942.00] | Mean: 5694905.75 |
| `transaction_count` | `int64` | 0.00% | 40 | Range: [20614.00 ➔ 45885.00] | Mean: 34945.65 |
| `date_x` | `object` | 0.00% | 40 | Likely Primary Key / Unique ID |
| `avg_transaction_value` | `float64` | 0.00% | 40 | Range: [117661.90 ➔ 225017.52] | Mean: 159278.52 |
| `avg_2015_transaction_value` | `float64` | 0.00% | 1 | Binary/Flag: {120911.01849400788: 40} |
| `avg_2015_transaction_count` | `float64` | 0.00% | 1 | Binary/Flag: {22627.25: 40} |
| `value_index` | `float64` | 0.00% | 40 | Range: [97.31 ➔ 186.10] | Mean: 131.73 |
| `volume_index` | `float64` | 0.00% | 40 | Range: [91.10 ➔ 202.79] | Mean: 154.44 |
| `portugal_asking_sale_m2` | `float64` | 0.00% | 40 | Range: [1038.33 ➔ 2781.00] | Mean: 1902.48 |
| `transaction_price_growth_yoy` | `float64` | 10.00% | 36 | Range: [-0.02 ➔ 0.15] | Mean: 0.07 |
| `avg_transaction_value_growth_yoy` | `float64` | 10.00% | 36 | Range: [-0.02 ➔ 0.15] | Mean: 0.07 |
| `price_growth_qoq` | `float64` | 2.50% | 39 | Range: [-0.01 ➔ 0.11] | Mean: 0.03 |
| `price_growth_yoy` | `float64` | 10.00% | 36 | Range: [0.05 ➔ 0.25] | Mean: 0.11 |
| `transaction_growth_qoq` | `float64` | 2.50% | 39 | Range: [-0.28 ➔ 0.35] | Mean: 0.02 |
| `transaction_growth_yoy` | `float64` | 10.00% | 36 | Range: [-0.28 ➔ 0.58] | Mean: 0.08 |
| `market_momentum` | `float64` | 10.00% | 36 | Range: [0.76 ➔ 1.68] | Mean: 1.15 |
| `market_acceleration_x` | `float64` | 12.50% | 35 | Range: [-0.34 ➔ 0.71] | Mean: 0.01 |
| `liquidity_signal` | `float64` | 0.00% | 40 | Range: [0.91 ➔ 2.03] | Mean: 1.54 |
| `pricing_pressure_index` | `float64` | 10.00% | 36 | Range: [-0.07 ➔ 0.16] | Mean: 0.04 |
| `valuation_signal` | `float64` | 10.00% | 36 | Range: [-0.16 ➔ 0.07] | Mean: -0.04 |
| `market_activity_index` | `float64` | 0.00% | 40 | Range: [91.10 ➔ 202.79] | Mean: 154.44 |
| `date_y` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `hpi_value` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `hpi_base100` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `hpi_change_qoq` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `hpi_change_yoy` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `hpi_ma_4` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `hpi_volatility_4` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `price_sqm_proxy` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `price_dispersion_proxy` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `price_trend_strength` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `liquidity_proxy` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `liquidity_growth` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `market_speed_proxy` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `market_acceleration_y` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `market_pressure_behavior` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `trend_momentum_behavior` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `market_regime` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `market_regime_enc` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `BPSTAT_interest_rate_of_new_business_volume_on_loans_for_` | `float64` | 37.50% | 23 | Range: [0.55 ➔ 4.89] | Mean: 2.13 |
| `date` | `object` | 75.00% | 10 | Top: '2015-01-01': 1 | '2016-01-01': 1 |
| `population_0_14` | `float64` | 75.00% | 10 | Range: [1359648.00 ➔ 1482804.00] | Mean: 1402520.20 |
| `population_15_64` | `float64` | 75.00% | 10 | Range: [6604819.00 ➔ 6753798.00] | Mean: 6667903.20 |
| `population_65_or_more` | `float64` | 75.00% | 10 | Range: [2145236.00 ➔ 2589960.00] | Mean: 2359760.60 |
| `economic_power_index` | `float64` | 75.00% | 10 | Range: [18.18 ➔ 18.74] | Mean: 18.42 |
| `unemployment_rate` | `float64` | 75.00% | 10 | Range: [6.10 ➔ 12.90] | Mean: 8.01 |
| `labor_stress` | `float64` | 75.00% | 10 | Range: [40399982.80 ➔ 87123994.20] | Mean: 53484739.96 |
| `housing_supply_total` | `float64` | 75.00% | 10 | Range: [7148.00 ➔ 25311.00] | Mean: 15282.00 |
| `supply_pressure` | `float64` | 75.00% | 10 | Range: [0.00 ➔ 0.00] | Mean: 0.00 |
| `construction_intensity` | `float64` | 75.00% | 10 | Range: [0.01 ➔ 0.01] | Mean: 0.01 |
| `urbanization_ratio` | `float64` | 75.00% | 5 | Range: [7.54 ➔ 10.08] | Mean: 8.04 |
| `building_value_index` | `float64` | 75.00% | 5 | Range: [11.37 ➔ 11.63] | Mean: 11.58 |
| `immigration_total` | `float64` | 75.00% | 9 | Range: [36849.00 ➔ 189367.00] | Mean: 99848.60 |
| `immigration_pressure` | `float64` | 75.00% | 10 | Range: [0.00 ➔ 0.02] | Mean: 0.01 |
| `macro_demand_index` | `float64` | 75.00% | 10 | Range: [5.28 ➔ 12.46] | Mean: 10.42 |
| `housing_imbalance` | `float64` | 75.00% | 10 | Range: [0.00 ➔ 0.02] | Mean: 0.01 |
| `socio_momentum` | `float64` | 75.00% | 10 | Range: [-0.52 ➔ 2.59] | Mean: 1.13 |
| `aging_ratio` | `float64` | 75.00% | 10 | Range: [0.32 ➔ 0.38] | Mean: 0.35 |
| `youth_ratio` | `float64` | 75.00% | 10 | Range: [0.20 ➔ 0.22] | Mean: 0.21 |


### 📄 Dataset: **AURA_MARKET_MASTER_V3.csv**
- **Sample Analyzed:** 100,000 rows
- **Total Features:** 80
| Feature Name | Data Type | Missing (%) | Unique Values | Distribution / Top Values |
|---|---|---|---|---|
| `Price` | `float64` | 0.20% | 770 | Range: [1250.00 ➔ 20000000.00] | Mean: 456900.60 |
| `Type` | `object` | 0.00% | 17 | Top: 'Apartment': 37320 | 'Land': 24200 |
| `TotalArea` | `float64` | 0.00% | 1,094 | Range: [3.00 ➔ 18600000.00] | Mean: 18546.37 |
| `LivingArea` | `float64` | 21.56% | 530 | Range: [0.00 ➔ 2396000.00] | Mean: 3269.83 |
| `GrossArea` | `float64` | 58.04% | 438 | Range: [0.00 ➔ 2716250.00] | Mean: 6211.32 |
| `NumberOfBedrooms` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `NumberOfBathrooms` | `float64` | 4.36% | 11 | Range: [0.00 ➔ 10.00] | Mean: 1.37 |
| `NumberOfWC` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `TotalRooms` | `float64` | 26.80% | 18 | Range: [0.00 ➔ 21.00] | Mean: 2.31 |
| `Parking` | `float64` | 0.68% | 4 | Range: [0.00 ➔ 3.00] | Mean: 0.86 |
| `HasParking` | `bool` | 0.00% | 2 | Binary/Flag: {False: 50200, True: 49800} |
| `Garage` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `Elevator` | `bool` | 0.00% | 2 | Binary/Flag: {False: 68480, True: 31520} |
| `ElectricCarsCharging` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `EnergyCertificate` | `object` | 0.00% | 10 | Top: 'NC': 44840 | 'A': 14200 |
| `EnergyEfficiencyLevel` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `ConstructionYear` | `float64` | 33.88% | 84 | Range: [1908.00 ➔ 2023.00] | Mean: 1993.60 |
| `City` | `object` | 0.00% | 49 | Top: 'Albufeira': 14640 | 'Portimão': 12360 |
| `Town` | `object` | 0.00% | 206 | Top: 'Albufeira e Olhos de Água': 12960 | 'Portimão': 10840 |
| `Price_per_sqm` | `float64` | 0.20% | 2,247 | Range: [0.05 ➔ 182333.33] | Mean: 1599.87 |
| `Room_Density` | `float64` | 26.80% | 682 | Range: [0.00 ➔ 0.75] | Mean: 0.01 |
| `Bathroom_Density` | `float64` | 35.56% | 37 | Range: [0.00 ➔ inf] | Mean: inf |
| `Property_Age` | `float64` | 33.88% | 84 | Range: [1.00 ➔ 116.00] | Mean: 30.40 |
| `Parking_Score` | `int64` | 0.00% | 3 | Range: [0.00 ➔ 2.00] | Mean: 0.99 |
| `Energy_Score` | `float64` | 0.00% | 10 | Range: [0.00 ➔ 10.00] | Mean: 3.19 |
| `Property_Score` | `float64` | 0.00% | 17 | Range: [0.00 ➔ 8.00] | Mean: 2.90 |
| `Municipality_Code` | `float64` | 5.68% | 49 | Range: [203.00 ➔ 4302.00] | Mean: 837.95 |
| `Parish_Code` | `object` | 5.68% | 160 | Top: '000nan': 18080 | '080106': 12960 |
| `Municipality_Name` | `object` | 5.68% | 49 | Top: 'Albufeira': 14640 | 'Portimão': 12360 |
| `Parish_Name` | `object` | 5.68% | 160 | Top: 'Total': 18080 | 'Albufeira e Olhos de Água': 12960 |
| `Population_Total` | `float64` | 23.80% | 154 | Range: [121.00 ➔ 68649.00] | Mean: 13956.15 |
| `Housing_Stock` | `float64` | 23.80% | 153 | Range: [111.00 ➔ 32939.00] | Mean: 13063.97 |
| `Vacant_Secondary_Homes` | `float64` | 23.80% | 145 | Range: [57.00 ➔ 22174.00] | Mean: 7244.09 |
| `Rental_Homes` | `float64` | 23.80% | 92 | Range: [0.00 ➔ 6567.00] | Mean: 1656.17 |
| `Buildings_Need_Repair` | `float64` | 23.80% | 141 | Range: [1.00 ➔ 3708.00] | Mean: 1393.58 |
| `Population_Density` | `float64` | 23.80% | 158 | Range: [2.12 ➔ 6152.09] | Mean: 387.20 |
| `Building_Density` | `float64` | 23.80% | 158 | Range: [4.09 ➔ 945.38] | Mean: 136.36 |
| `Young_Population_Ratio` | `float64` | 23.80% | 156 | Range: [0.03 ➔ 0.30] | Mean: 0.21 |
| `Elderly_Population_Ratio` | `float64` | 23.80% | 156 | Range: [0.14 ➔ 0.69] | Mean: 0.27 |
| `_cat1_row_id` | `int64` | 0.00% | 2,500 | Range: [0.00 ➔ 2499.00] | Mean: 1249.50 |
| `year` | `int64` | 0.00% | 10 | Range: [2015.00 ➔ 2024.00] | Mean: 2019.50 |
| `quarter` | `int64` | 0.00% | 4 | Range: [1.00 ➔ 4.00] | Mean: 2.50 |
| `cat2_date` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `cat2_hpi_value` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `cat2_hpi_base100` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `cat2_hpi_change_qoq` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `cat2_hpi_change_yoy` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `cat2_hpi_ma_4` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `cat2_hpi_volatility_4` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `cat2_price_sqm_proxy` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `cat2_price_dispersion_proxy` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `cat2_price_trend_strength` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `cat2_liquidity_proxy` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `cat2_liquidity_growth` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `cat2_market_speed_proxy` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `cat2_market_acceleration` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `cat2_market_pressure_behavior` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `cat2_trend_momentum_behavior` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `cat2_market_regime` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `cat2_market_regime_enc` | `float64` | 100.00% | 0 | Binary/Flag: {} |
| `cat3_interest_rate_of_new_business_volume_on_loans_for_` | `float64` | 37.50% | 23 | Range: [0.55 ➔ 4.89] | Mean: 2.13 |
| `cat4_date` | `object` | 75.00% | 10 | Top: '2015-01-01': 2500 | '2016-01-01': 2500 |
| `cat4_population_0_14` | `float64` | 75.00% | 10 | Range: [1359648.00 ➔ 1482804.00] | Mean: 1402520.20 |
| `cat4_population_15_64` | `float64` | 75.00% | 10 | Range: [6604819.00 ➔ 6753798.00] | Mean: 6667903.20 |
| `cat4_population_65_or_more` | `float64` | 75.00% | 10 | Range: [2145236.00 ➔ 2589960.00] | Mean: 2359760.60 |
| `cat4_economic_power_index` | `float64` | 75.00% | 10 | Range: [18.18 ➔ 18.74] | Mean: 18.42 |
| `cat4_unemployment_rate` | `float64` | 75.00% | 10 | Range: [6.10 ➔ 12.90] | Mean: 8.01 |
| `cat4_labor_stress` | `float64` | 75.00% | 10 | Range: [40399982.80 ➔ 87123994.20] | Mean: 53484739.96 |
| `cat4_housing_supply_total` | `float64` | 75.00% | 10 | Range: [7148.00 ➔ 25311.00] | Mean: 15282.00 |
| `cat4_supply_pressure` | `float64` | 75.00% | 10 | Range: [0.00 ➔ 0.00] | Mean: 0.00 |
| `cat4_construction_intensity` | `float64` | 75.00% | 10 | Range: [0.01 ➔ 0.01] | Mean: 0.01 |
| `cat4_urbanization_ratio` | `float64` | 75.00% | 5 | Range: [7.54 ➔ 10.08] | Mean: 8.04 |
| `cat4_building_value_index` | `float64` | 75.00% | 5 | Range: [11.37 ➔ 11.63] | Mean: 11.58 |
| `cat4_immigration_total` | `float64` | 75.00% | 9 | Range: [36849.00 ➔ 189367.00] | Mean: 99848.60 |
| `cat4_immigration_pressure` | `float64` | 75.00% | 10 | Range: [0.00 ➔ 0.02] | Mean: 0.01 |
| `cat4_macro_demand_index` | `float64` | 75.00% | 10 | Range: [5.28 ➔ 12.46] | Mean: 10.42 |
| `cat4_housing_imbalance` | `float64` | 75.00% | 10 | Range: [0.00 ➔ 0.02] | Mean: 0.01 |
| `cat4_socio_momentum` | `float64` | 75.00% | 10 | Range: [-0.52 ➔ 2.59] | Mean: 1.13 |
| `cat4_aging_ratio` | `float64` | 75.00% | 10 | Range: [0.32 ➔ 0.38] | Mean: 0.35 |
| `cat4_youth_ratio` | `float64` | 75.00% | 10 | Range: [0.20 ➔ 0.22] | Mean: 0.21 |


## 📁 System Component: `Aura -Datasets -Final Version\Dataset C Final`

### 📄 Dataset: **aura_cat6_tourism_aggregated.csv**
- **Sample Analyzed:** 16 rows
- **Total Features:** 10
| Feature Name | Data Type | Missing (%) | Unique Values | Distribution / Top Values |
|---|---|---|---|---|
| `municipality` | `object` | 0.00% | 16 | Likely Primary Key / Unique ID |
| `airbnb_listing_count` | `int64` | 0.00% | 16 | Range: [11.00 ➔ 17112.00] | Mean: 1559.38 |
| `airbnb_unique_host_count` | `int64` | 0.00% | 16 | Range: [6.00 ➔ 5965.00] | Mean: 641.00 |
| `airbnb_avg_price_per_night` | `float64` | 0.00% | 16 | Range: [94.25 ➔ 257.33] | Mean: 175.01 |
| `airbnb_avg_occupancy_rate` | `float64` | 0.00% | 16 | Range: [9.00 ➔ 90.67] | Mean: 41.02 |
| `airbnb_avg_review_count` | `float64` | 0.00% | 16 | Range: [8.00 ➔ 90.22] | Mean: 30.26 |
| `airbnb_avg_review_score` | `float64` | 0.00% | 16 | Range: [4.32 ➔ 4.85] | Mean: 4.71 |
| `year` | `int64` | 0.00% | 1 | Binary/Flag: {2026: 16} |
| `quarter` | `int64` | 0.00% | 1 | Binary/Flag: {1: 16} |
| `period` | `object` | 0.00% | 1 | Top: '2026-Q1': 16 |


### 📄 Dataset: **aura_cat6_tourism_raw.csv**
- **Sample Analyzed:** 24,950 rows
- **Total Features:** 78
| Feature Name | Data Type | Missing (%) | Unique Values | Distribution / Top Values |
|---|---|---|---|---|
| `id` | `int64` | 0.00% | 24,950 | Range: [6499.00 ➔ 1649209494360086528.00] | Mean: 655947123264947200.00 |
| `airbnb_listing_url` | `object` | 0.00% | 24,950 | Likely Primary Key / Unique ID |
| `airbnb_scrape_id` | `int64` | 0.00% | 1 | Binary/Flag: {20260326033101: 24950} |
| `airbnb_last_scraped` | `object` | 0.00% | 8 | Top: '2026-04-02': 9316 | '2026-03-30': 3276 |
| `airbnb_source` | `object` | 0.00% | 2 | Top: 'city scrape': 19699 | 'previous scrape': 5251 |
| `airbnb_name` | `object` | 0.00% | 24,148 | Top: 'Excelente Quarto Central': 48 | 'Quarto Duplo': 13 |
| `airbnb_description` | `object` | 2.81% | 20,383 | Top: 'Our mission is to empower individuals to immerse themselves in new places by having a home wherever they go. We do this by providing artfully designed fully furnished and serviced apartments for stays of one month or more. We are currently present in some of the most important cities in Europe.': 171 | 'Keep it simple at this peaceful and centrally-located place.': 105 |
| `airbnb_picture_url` | `object` | 0.00% | 24,616 | Top: 'https://a0.muscache.com/pictures/miso/Hosting-1136149013103355650/original/84e37c02-553e-4c2d-9b74-bedfb71ae679.jpeg': 12 | 'https://a0.muscache.com/pictures/miso/Hosting-578123222977240477/original/ea6af04d-64ce-46ad-8a3a-ec1519619191.jpeg': 9 |
| `airbnb_host_id` | `int64` | 0.00% | 9,715 | Range: [14455.00 ➔ 753249454.00] | Mean: 234372709.91 |
| `airbnb_host_url` | `object` | 0.00% | 9,715 | Top: 'https://www.airbnb.com/users/show/3953109': 285 | 'https://www.airbnb.com/users/show/505424337': 236 |
| `airbnb_host_profile_id` | `float64` | 0.18% | 9,699 | Range: [1462506753508551936.00 ➔ 1648675645305211392.00] | Mean: 1469789894042520064.00 |
| `airbnb_host_profile_url` | `object` | 0.22% | 9,700 | Top: 'https://www.airbnb.com/users/profile/1462643483408725552': 284 | 'https://www.airbnb.com/users/profile/1470272044642386863': 236 |
| `airbnb_host_name` | `object` | 0.18% | 3,977 | Top: 'Pedro': 690 | 'Maria': 629 |
| `airbnb_hosts_time_as_user_years` | `float64` | 0.18% | 17 | Range: [0.00 ➔ 16.00] | Mean: 7.36 |
| `airbnb_hosts_time_as_user_months` | `float64` | 0.18% | 12 | Range: [0.00 ➔ 11.00] | Mean: 5.91 |
| `airbnb_hosts_time_as_host_years` | `float64` | 0.18% | 16 | Range: [0.00 ➔ 15.00] | Mean: 6.47 |
| `airbnb_hosts_time_as_host_months` | `float64` | 0.18% | 12 | Range: [0.00 ➔ 11.00] | Mean: 6.02 |
| `airbnb_host_location` | `object` | 29.88% | 591 | Top: 'Lisbon, Portugal': 11287 | 'Cascais, Portugal': 675 |
| `airbnb_host_about` | `object` | 44.36% | 4,228 | Top: 'We are Feels Like Home Holiday Rentals.
A company that was born with a unique purpose: to bring you the best living experience during your trip to Portugal.
That’s right we want you to feel like home! We offer beautifully furnished, well-located apartments and houses for your holiday or business stay. We're ideal for travelers who enjoy sleeping in comfortable homes at comfortable prices!
We offer you options!
Choose from over 500 carefully selected properties in Portugal, suited for every taste and every occasion. From studios to rustic country homes to sleek city duplexes, whether it´s in Algarve, Ericeira, Lisbon, Madeira, Porto, or somewhere in between, we have a property that's right for you!': 285 | 'At Smith&Adams, we believe every guest deserves a seamless and stress-free stay.
Our mission is to provide top-tier service, fast communication, and full availability to ensure your experience is nothing short of exceptional.

With a strong focus on hospitality and attention to detail, we pride ourselves on always being there for you. 

Our team is ready to assist your inquiries or questions, and go the extra mile to make your stay unforgettable.': 220 |
| `airbnb_host_is_superhost` | `object` | 0.18% | 2 | Top: 'f': 16855 | 't': 8051 |
| `airbnb_host_picture_url` | `object` | 0.18% | 9,325 | Top: 'https://a0.muscache.com/im/pictures/user/9341b45f-d1bd-434f-964e-d3097e339c75.jpg?aki_policy=profile_x_medium': 285 | 'https://a0.muscache.com/im/pictures/user/User/original/b870280f-d454-4506-b637-7986dc1ba293.jpeg?aki_policy=profile_x_medium': 236 |
| `airbnb_host_listings_count` | `float64` | 0.18% | 116 | Range: [0.00 ➔ 2625.00] | Mean: 35.39 |
| `airbnb_host_has_profile_pic` | `object` | 0.18% | 2 | Top: 't': 24293 | 'f': 613 |
| `airbnb_host_identity_verified` | `object` | 0.18% | 2 | Top: 't': 24362 | 'f': 544 |
| `airbnb_neighbourhood_cleansed` | `object` | 0.00% | 130 | Top: 'Santa Maria Maior': 3606 | 'Misericrdia': 2629 |
| `neighbourhood_group_cleansed` | `object` | 0.00% | 16 | Top: 'Lisboa': 17112 | 'Cascais': 2371 |
| `latitude` | `float64` | 0.00% | 15,096 | Range: [38.68 ➔ 39.30] | Mean: 38.76 |
| `longitude` | `float64` | 0.00% | 16,239 | Range: [-9.49 ➔ -8.86] | Mean: -9.21 |
| `airbnb_property_type` | `object` | 0.00% | 86 | Top: 'Entire rental unit': 14036 | 'Private room in rental unit': 3738 |
| `airbnb_room_type` | `object` | 0.00% | 4 | Top: 'Entire home/apt': 18464 | 'Private room': 6154 |
| `airbnb_accommodates` | `int64` | 0.00% | 16 | Range: [1.00 ➔ 16.00] | Mean: 3.79 |
| `airbnb_bathrooms` | `float64` | 21.07% | 26 | Range: [0.00 ➔ 23.00] | Mean: 1.46 |
| `airbnb_bathrooms_text` | `object` | 0.08% | 49 | Top: '1 bath': 12615 | '2 baths': 3587 |
| `airbnb_bedrooms` | `float64` | 4.73% | 20 | Range: [0.00 ➔ 43.00] | Mean: 1.70 |
| `airbnb_beds` | `float64` | 21.18% | 30 | Range: [0.00 ➔ 45.00] | Mean: 2.45 |
| `airbnb_amenities` | `object` | 0.00% | 22,639 | Top: '["Hot water", "Self check-in", "Wifi", "Kitchen", "Smart lock", "Essentials", "Washer", "Dedicated workspace", "Lock on bedroom door"]': 69 | '[]': 67 |
| `airbnb_price` | `object` | 13.96% | 5,270 | Top: '$80.00': 156 | '$120.00': 133 |
| `airbnb_price_quote_checkin_date` | `object` | 10.78% | 321 | Top: '2026-04-05': 1534 | '2026-04-06': 1266 |
| `airbnb_price_quote_checkout_date` | `object` | 10.78% | 344 | Top: '2026-04-07': 1249 | '2026-04-06': 1120 |
| `airbnb_price_quote_total_price` | `float64` | 14.03% | 4,561 | Range: [14.00 ➔ 57855.00] | Mean: 587.41 |
| `airbnb_price_quote_price_per_night` | `float64` | 14.03% | 5,269 | Range: [2.61 ➔ 18247.00] | Mean: 186.79 |
| `airbnb_price_quote_raw` | `object` | 10.78% | 19,341 | Top: '{"quote": {"taxes": null, "currency": null, "date_match": null, "service_fee": null, "total_price": null, "cleaning_fee": null, "is_available": false, "discount_amount": null, "price_per_night": null, "nightly_subtotal": null, "discounted_subtotal": null, "raw_price_line_items": [], "returned_checkin_date": null, "requested_checkin_date": "2026-04-02", "returned_checkout_date": null, "requested_checkout_date": "2026-04-03"}}': 88 | '{"quote": {"taxes": null, "currency": null, "date_match": null, "service_fee": null, "total_price": null, "cleaning_fee": null, "is_available": false, "discount_amount": null, "price_per_night": null, "nightly_subtotal": null, "discounted_subtotal": null, "raw_price_line_items": [], "returned_checkin_date": null, "requested_checkin_date": "2026-03-29", "returned_checkout_date": null, "requested_checkout_date": "2026-03-30"}}': 60 |
| `airbnb_minimum_nights` | `float64` | 0.07% | 61 | Range: [1.00 ➔ 1000.00] | Mean: 4.06 |
| `airbnb_maximum_nights` | `float64` | 0.07% | 160 | Range: [1.00 ➔ 36180.00] | Mean: 628.37 |
| `airbnb_minimum_minimum_nights` | `float64` | 0.07% | 61 | Range: [1.00 ➔ 1000.00] | Mean: 4.06 |
| `airbnb_maximum_minimum_nights` | `float64` | 0.07% | 80 | Range: [1.00 ➔ 1000.00] | Mean: 7.24 |
| `airbnb_minimum_maximum_nights` | `float64` | 0.07% | 158 | Range: [1.00 ➔ 36180.00] | Mean: 546.38 |
| `airbnb_maximum_maximum_nights` | `float64` | 0.07% | 160 | Range: [1.00 ➔ 36180.00] | Mean: 628.37 |
| `airbnb_minimum_nights_avg_ntm` | `float64` | 0.00% | 320 | Range: [1.00 ➔ 1000.00] | Mean: 4.93 |
| `airbnb_maximum_nights_avg_ntm` | `float64` | 0.00% | 1,914 | Range: [1.00 ➔ 36180.00] | Mean: 577.30 |
| `airbnb_has_availability` | `object` | 3.13% | 2 | Top: 't': 24132 | 'f': 36 |
| `airbnb_availability_30` | `int64` | 0.00% | 31 | Range: [0.00 ➔ 30.00] | Mean: 11.34 |
| `airbnb_availability_60` | `int64` | 0.00% | 61 | Range: [0.00 ➔ 60.00] | Mean: 25.54 |
| `airbnb_availability_90` | `int64` | 0.00% | 91 | Range: [0.00 ➔ 90.00] | Mean: 42.97 |
| `airbnb_availability_365` | `int64` | 0.00% | 366 | Range: [0.00 ➔ 365.00] | Mean: 214.29 |
| `airbnb_calendar_last_scraped` | `object` | 0.00% | 8 | Top: '2026-04-02': 7233 | '2026-03-30': 3700 |
| `airbnb_number_of_reviews` | `int64` | 0.00% | 687 | Range: [0.00 ➔ 1909.00] | Mean: 73.42 |
| `airbnb_number_of_reviews_ltm` | `int64` | 0.00% | 147 | Range: [0.00 ➔ 402.00] | Mean: 13.57 |
| `airbnb_number_of_reviews_l30d` | `int64` | 0.00% | 23 | Range: [0.00 ➔ 25.00] | Mean: 0.75 |
| `airbnb_availability_eoy` | `int64` | 0.00% | 282 | Range: [0.00 ➔ 281.00] | Mean: 164.95 |
| `airbnb_number_of_reviews_ly` | `int64` | 0.00% | 145 | Range: [0.00 ➔ 357.00] | Mean: 13.68 |
| `airbnb_estimated_occupancy_l365d` | `int64` | 0.00% | 94 | Range: [0.00 ➔ 255.00] | Mean: 77.29 |
| `airbnb_estimated_revenue_l365d` | `float64` | 13.96% | 8,683 | Range: [0.00 ➔ 303804.00] | Mean: 13295.91 |
| `airbnb_first_review` | `object` | 13.37% | 4,154 | Top: '2025-04-20': 40 | '2019-04-21': 39 |
| `airbnb_last_review` | `object` | 13.37% | 1,764 | Top: '2026-03-15': 502 | '2026-03-16': 413 |
| `airbnb_review_scores_rating` | `float64` | 13.37% | 163 | Range: [1.00 ➔ 5.00] | Mean: 4.65 |
| `airbnb_review_scores_accuracy` | `float64` | 13.37% | 153 | Range: [0.00 ➔ 5.00] | Mean: 4.71 |
| `airbnb_review_scores_cleanliness` | `float64` | 13.37% | 173 | Range: [0.00 ➔ 5.00] | Mean: 4.68 |
| `airbnb_review_scores_checkin` | `float64` | 13.37% | 155 | Range: [0.00 ➔ 5.00] | Mean: 4.77 |
| `airbnb_review_scores_communication` | `float64` | 13.37% | 142 | Range: [1.00 ➔ 5.00] | Mean: 4.78 |
| `airbnb_review_scores_location` | `float64` | 13.37% | 167 | Range: [1.00 ➔ 5.00] | Mean: 4.70 |
| `airbnb_review_scores_value` | `float64` | 13.37% | 174 | Range: [1.00 ➔ 5.00] | Mean: 4.57 |
| `airbnb_license` | `object` | 4.87% | 13,545 | Top: 'Exempt': 4493 | '14829': 85 |
| `airbnb_calculated_host_listings_count` | `int64` | 0.00% | 63 | Range: [1.00 ➔ 285.00] | Mean: 22.36 |
| `airbnb_calculated_host_listings_count_entire_homes` | `int64` | 0.00% | 56 | Range: [0.00 ➔ 276.00] | Mean: 15.66 |
| `airbnb_calculated_host_listings_count_private_rooms` | `int64` | 0.00% | 35 | Range: [0.00 ➔ 227.00] | Mean: 6.57 |
| `airbnb_calculated_host_listings_count_shared_rooms` | `int64` | 0.00% | 9 | Range: [0.00 ➔ 12.00] | Mean: 0.05 |
| `airbnb_reviews_per_month` | `float64` | 13.37% | 769 | Range: [0.01 ➔ 28.76] | Mean: 1.46 |


### 📄 Dataset: **aura_cat7_volatility_backbone.csv**
- **Sample Analyzed:** 1,535 rows
- **Total Features:** 9
| Feature Name | Data Type | Missing (%) | Unique Values | Distribution / Top Values |
|---|---|---|---|---|
| `municipality` | `object` | 0.00% | 57 | Top: 'Albufeira': 28 | 'Alcochete': 28 |
| `code` | `object` | 0.00% | 57 | Top: '1500801': 28 | '1B01502': 28 |
| `volatility_time` | `object` | 0.00% | 28 | Top: 'unnamed:_5': 56 | 'unnamed:_13': 56 |
| `volatility_price_per_m2` | `float64` | 0.00% | 1,138 | Range: [551.00 ➔ 5198.00] | Mean: 1884.67 |
| `year` | `int64` | 0.00% | 14 | Range: [2019.00 ➔ 2032.00] | Mean: 2025.49 |
| `quarter` | `int64` | 0.00% | 2 | Binary/Flag: {3: 771, 1: 764} |
| `volatility_price_growth` | `float64` | 0.00% | 1,463 | Range: [-0.51 ➔ 0.59] | Mean: -0.03 |
| `volatility_price_trend` | `float64` | 0.00% | 1,289 | Range: [651.67 ➔ 5021.00] | Mean: 1836.13 |
| `volatility_price_volatility` | `float64` | 0.00% | 1,361 | Range: [8.14 ➔ 719.14] | Mean: 100.81 |

