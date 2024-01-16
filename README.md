# 📁 CSV Reader Project

## Overview
This simple Rust project demonstrates a CSV file reader using the `csv` crate. It provides a basic example of reading data from a CSV file and printing the records to the console.

## Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/itsmohitnarayan/CSV-Reader-Rust.git
   cd csv-reader-rust
   ```

2. Run the project:
   ```bash
   cargo run
   ```

3. Ensure that a CSV file named `customers.csv` exists in the project directory. Modify the file path in the `main` function if your CSV file is located elsewhere.

## Dependencies
- [csv](https://crates.io/crates/csv): A CSV parsing library for Rust.

## Installation
Add the following dependency to your `Cargo.toml` file:
```toml
[dependencies]
csv = "1.1"
```

## Code Snippet
```rust
use std::error::Error;
use csv;

fn read_from_file(path: &str) -> Result<(), Box<dyn Error>>{
    let mut reader = csv::Reader::from_path(path)?;

    for result in reader.records(){
        let record = result?;
        println!("{:?}", record);
    }
    Ok(())
}

fn main() {
    if let Err(e) = read_from_file("./customers.csv"){
        eprintln!("{}", e);
    }
}
```

## License
This project is licensed under the [MIT License](LICENSE). Feel free to use and modify it according to your needs.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
