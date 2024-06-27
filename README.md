# Race Data Processor

This Rust program processes race data from a CSV file, converts it into a specified data structure, and outputs the result to a text file. The data is sorted by timestamp to ensure chronological order.

## Overview

The program reads a CSV file containing race data with columns for timestamp, LED number, and driver number. It processes this data into a `VisualizationData` structure that contains a list of `UpdateFrame` structures. Each `UpdateFrame` includes a list of `DriverData`, representing the state of the race at each timestamp.

## Data Structure

The program uses the following data structures:

```rust
#[derive(Debug)]
struct DriverData {
    driver_number: u32,
    led_num: u32,
}

#[derive(Debug)]
struct UpdateFrame {
    drivers: Vec<DriverData>,
}

#[derive(Debug)]
struct VisualizationData {
    update_rate_ms: u32,
    frames: Vec<UpdateFrame>,
}
