# Unzip File
```python
with zipfile.ZipFile(zip_file) as z:
    with z.open(file_inside_zip) as f:
        df = pd.read_csv(f)
```
# CSV File
```python
pd.read_csv(csv_file_path) 
```