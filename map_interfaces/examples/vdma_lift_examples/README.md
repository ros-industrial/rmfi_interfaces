# LIF 1.0.0 guideline examples

These are the 19 example LIF files from section 10 [VDMA LIF 1.0.0, March 2024](https://vdma.eu/documents/34570/3317035/FuI_Guideline_LIF_GB.pdf).
Page numbers are the printed page numbers in that PDF.

| File | Section | Title | Page |
|---|---|---|---|
| `10-01_forward_edge.json` | 10.1 | Forward Edge | 26 |
| `10-02_bidirectional_edge.json` | 10.2 | Bidirectional Edge | 28 |
| `10-03_counter_clockwise_rotation_on_node.json` | 10.3 | Counter-clockwise Rotation on Node | 30 |
| `10-04_omnidirectional_edge.json` | 10.4 | Omnidirectional Edge | 32 |
| `10-05_multiple_layouts_in_one_lif_file.json` | 10.5 | Multiple Layouts in One LIF File | 34 |
| `10-06_station_with_one_node.json` | 10.6 | Station with One Node | 37 |
| `10-07_station_with_two_nodes.json` | 10.7 | Station with Two Nodes | 40 |
| `10-08_station_with_two_nodes_restricted_for_different_vehicle_types.json` | 10.8 | Station with Two Nodes, Restricted for Different Vehicle Types | 45 |
| `10-09_rotation_station.json` | 10.9 | Rotation Station | 49 |
| `10-10_station_with_three_nodes_restricted_to_different_vehicle_types.json` | 10.10 | Station with Three Nodes, Restricted to Different Vehicle Types | 53 |
| `10-11_multiple_edges_with_load_restrictions.json` | 10.11 | Multiple Edges with Load Restrictions | 59 |
| `10-12_multiple_edges_between_same_two_nodes_for_different_vehicletypeedgeproperty.json` | 10.12 | Multiple Edges Between Same Two Nodes for Different vehicleTypeEdge Property Constraints | 65 |
| `10-13_battery_charging_station.json` | 10.13 | Battery Charging Station | 69 |
| `10-14_two_levels_of_a_facility_in_one_lif_file.json` | 10.14 | Two Levels of a Facility in One LIF File | 72 |
| `10-15_rack_station_modelled_by_three_stations.json` | 10.15 | Rack Station Modelled by Three Stations | 76 |
| `10-16_rack_station_modelled_by_three_nodes.json` | 10.16 | Rack Station Modelled by Three Nodes | 79 |
| `10-17_edge_with_trajectory_definition.json` | 10.17 | Edge with Trajectory Definition | 84 |
| `10-18_manufacturer_specific_action_on_an_edge.json` | 10.18 | Manufacturer Specific Action on an Edge | 88 |
| `10-19_forward_edge_with_two_vehicle_types_with_differing_orientation.json` | 10.19 | Forward Edge with Two Vehicle Types with Differing Orientation | 91 |

## LIF Examples Schema Validation Report

All 19 examples fail. Each failure is one of the two errors described under Findings.

| Section | Example | Result | Errors | Error |
| --- | --- | --- | --- | --- |
| 10.1 | Forward Edge | Fail | 1 | `stations` missing |
| 10.2 | Bidirectional Edge | Fail | 1 | `stations` missing |
| 10.3 | Counter-clockwise Rotation on Node | Fail | 1 | `stations` missing |
| 10.4 | Omnidirectional Edge | Fail | 1 | `stations` missing |
| 10.5 | Multiple Layouts in One LIF File | Fail | 2 | `stations` missing in both layouts |
| 10.6 | Station with One Node | Fail | 1 | `stationHeight` is `"0.55"` |
| 10.7 | Station with Two Nodes | Fail | 1 | `stationHeight` is `"0.55"` |
| 10.8 | Station with Two Nodes, Restricted for Different Vehicle Types | Fail | 1 | `stationHeight` is `"0.0"` |
| 10.9 | Rotation Station | Fail | 1 | `stationHeight` is `"0.75"` |
| 10.10 | Station with Three Nodes, Restricted to Different Vehicle Types | Fail | 1 | `stationHeight` is `"0.5"` |
| 10.11 | Multiple Edges with Load Restrictions | Fail | 1 | `stations` missing |
| 10.12 | Multiple Edges Between Same Two Nodes | Fail | 1 | `stations` missing |
| 10.13 | Battery Charging Station | Fail | 1 | `stationHeight` is `"0.0"` |
| 10.14 | Two Levels of a Facility in One LIF File ────────────────────────── | Fail | 2 | `stations` missing in both layouts |
| 10.15 | Rack Station Modelled by Three Stations | Fail | 3 | `stationHeight` is `"0.0"`, `"2.5"`, `"5.0"` |
| 10.16 | Rack Station Modelled by Three Nodes | Fail | 3 | `stationHeight` is `"0.0"`, `"2.5"`, `"5.0"` |
| 10.17 | Edge with Trajectory Definition | Fail | 1 | `stations` missing |
| 10.18 | Manufacturer Specific Action on an Edge | Fail | 1 | `stations` missing |
| 10.19 | Forward Edge with Two Vehicle Types with Differing Orientation | Fail | 1 | `stations` missing |

Total: 19 of 19 fail, with 25 errors.

## Known problems in the examples

The examples are left as printed, so they break two rules from the
guideline's own tables (section 8.3):

- **`stations` is missing** in 11 examples (10.1–10.5, 10.11, 10.12, 10.14,
  10.17–10.19). Table 8.3.3 (page 12) does not mark `stations` as optional.
- **`stationHeight` is a string** (for example `"0.55"`) in all 8 examples
  that have stations. Table 8.3.13 (page 22) gives its type as float64.
