### 🏷️ `label_data()`

This function applies **variable labels** to a REDCap dataset using a formatted **data dictionary** (e.g., generated from `read_data_dict()`).

Labeling variables makes data easier to understand during analysis by providing human-readable descriptions of what each field represents.

#### 💡 Link to Code: https://github.com/NUMesCtrData/Label-Data-Frame/blob/main/label_data
---

#### ⚙️ Usage

```r
labeled_df <- label_data(data_dict, data)
```

- `data_dict`: A data frame containing at least the columns `field_name` and `field_label`. Typically created by `read_data_dict()`.
- `data`: A REDCap-exported data frame whose columns will be labeled.

---

#### ✅ Example

```r
df <- label_data(data_dict, df)
```

After labeling, functions like `summary()`, `str()`, or `Hmisc::describe()` will display the human-readable labels for variables.

---

#### 🔍 How It Works

- Iterates through each row of `data_dict`.
- For each variable in `field_name`, assigns the corresponding `field_label` using `Hmisc::var_label()`.
- Returns the **labeled** version of the dataset.

---

#### 📦 Requirements

- Requires the `Hmisc` package for `var_label()`.

---

#### 💡 Tip

Once labeled, try using:

```r
Hmisc::describe(labeled_df)
```

to see the labeled summary of your dataset.
