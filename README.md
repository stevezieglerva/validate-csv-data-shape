# validate-csv-data-shape

📈 Validates the shape of the numerical fields of data in a CSV file to make sure the average or standard deviation is similar to expected values. Existing CSV validators check row counts, field definitions, and data values. But, they do not check if they data has changed significantly from expected values. This could help detect upstream data generation issues.

# Pre-reqs
```python
pip install -r requirements.txt
```

# Usage

```python
> filename = "tests/data/test_single_column.csv"
> field_stats = [
    FieldStats(name="cola", delta_threshold=0.1, average=4, std_dev=3.32)
]

> results = validate_csv_shape(filename, field_stats)
> print(results)

["cola.average of 5.0 is not similar to 4"]
```
