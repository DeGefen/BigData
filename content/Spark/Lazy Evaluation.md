---
aliases:
  - Lazy Execution
  - Lazy
  - מאוחרות לביצוע
---
>(Or Lazy Execution) Is a core optimization concept in [[Apache Spark]] where operations are **not executed immediately** when they are called. Instead, Spark builds an **execution plan (DAG)** and **waits** until it needs the result to actually run the computations.

>In Hebrew: ***״מאוחרות לביצוע״***
## Why Use Lazy Evaluation?

1. **Optimization**  
   Spark can analyze the entire chain of operations and **optimize execution** (e.g., combine steps, skip unnecessary work).

2. **Efficiency**  
   Unused data or unnecessary computations are never executed, **saving resources**.

3. **Fault Tolerance**  
   Since transformations are recorded and not executed, Spark can **recalculate data** if a node fails, using the original lineage.

## How It Works

### Step-by-Step

```python
# Step 1: Read file (no action yet)
rdd = sc.textFile("log.txt")

# Step 2: Define a transformation (still no action)
errors = rdd.filter(lambda line: "ERROR" in line)

# Step 3: Trigger an action (everything runs now)
errors_count = errors.count()
```

