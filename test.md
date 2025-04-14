### Title:
Laravel Collections: The Real Difference Between `map()` and `filter()` 💡

---

### How we often get confused:
Laravel developers sometimes use `map()` and `filter()` interchangeably, thinking they both just "loop and return something" — but that's **not true**!

Let’s break it down with simple examples and the right use cases 👇

---

### 🔁 `map()` – Modify Every Item
> Use this when you want to transform or change every item in a collection.

```php
$prices = collect([100, 200, 300]);

$withGST = $prices->map(function ($price) {
    return $price * 1.18;
});

// Output: [118, 236, 354]
```
- ✅ Same number of items
- ✅ Each item is transformed
- ❌ No items are removed

---

### 🔍 `filter()` – Select Only What You Need
> Use this when you want to remove unwanted items based on a condition.

```php
$prices = collect([100, 200, 300]);

$greaterThan150 = $prices->filter(function ($price) {
    return $price > 150;
});

// Output: [200, 300]
```
- ❌ Number of items can reduce
- ✅ Keeps only items matching the condition
- ❌ Items are not modified

---

### 🔄 Combo Usage (Real Power 💪)

```php
$collection = collect([10, 20, 30, 40, 50]);

$result = $collection
    ->filter(fn($item) => $item > 25)   // [30, 40, 50]
    ->map(fn($item) => $item * 2);      // [60, 80, 100]
```

Perfect when you want to clean your data and then transform it!

---

### 🔎 Summary:

| Method    | Purpose                   | Modifies Items | Removes Items | Return Length |
|-----------|----------------------------|----------------|----------------|----------------|
| `map()`   | Transform each item        | ✅ Yes         | ❌ No          | Same as input |
| `filter()`| Keep items matching logic  | ❌ No          | ✅ Yes         | Can be smaller|

---

### 🧠 Where it's used in real projects:
- Cleaning data from APIs
- Modifying prices or product attributes
- Filtering users based on roles/status
- Preparing data before exporting to Excel

---

### #Tags:
#Laravel #PHP #LaravelTips #WebDevelopment #CleanCode #Collections #MapVsFilter #IndianDevs #CodeSmarter #Laravel12

