# 🛠️ Data Pipeline: CSV to SQLite (ETL)

This project implements a simple yet robust **ETL (Extract, Transform, Load)** pipeline that processes a retail transactions dataset. The pipeline reads a raw CSV file, cleans and transforms the data, and loads it into a local SQLite database. It includes basic validation to ensure data integrity.

---

## 📦 Features

- ✅ **Extracts** data from a CSV file using `pandas`.
- 🔄 **Transforms** data by:
  - Dropping rows with missing product names.
  - Replacing missing store names with `"Undesignated store"`.
  - Converting timestamp strings to timedeltas and filling missing values with the median.
- 🗄️ **Loads** the clean dataset into a SQLite database.

---

## 🧾 Data Assumptions

- Input CSV file contains columns including:
  - `Purchase__product__name`
  - `Purchase__product__price`
  - `Purchase__product__quantity`
  - `Purchase__storeName`
  - `Purchase__timeStamp` (in `MM:SS` or `M:SS` format)
- Missing timestamps are assumed to be **Missing Not At Random (MNAR)** and are filled using the **median**.
- Missing store names are replaced with `"Undesignated store"`.

---

## 🧪 Requirements

- Python 3.7+
- Libraries:
  - `pandas`
  - `numpy`
  - `sqlite3` (standard library)

Install dependencies:
pip install pandas numpy


## 🚀 How to Run

1. Place your CSV file (e.g., `DataAnalystTask.csv`) in the root directory.
2. Run the notebook `pipeline.ipynb` in Jupyter Notebook, or convert it into a `.py` script and run it as:

Then run
python pipeline.py


## 📁 Output

- `Data_Pipeline` SQLite database containing a single cleaned table:
  - `Store_Purchase`