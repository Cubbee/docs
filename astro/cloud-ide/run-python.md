---
sidebar_label: Write Python
title: Write Python in the Astro Cloud IDE
id: run-python
description: Learn how to run Python code by creating and configuring Python cells in the Astro Cloud IDE.
---

A Python cell contains a Python function that you can run in isolation or as a dependency in your pipeline. Create Python cells to execute Python as part of your data pipeline. 

## Prerequisites 

- An IDE project and pipeline. See [Step 2: Create a pipeline](/astro/cloud-ide/quickstart.md#step-2-create-a-pipeline).

## Create a Python cell

1. In the Cloud UI, select a Workspace and then select Cloud IDE.

2. Select a project.

3. On the **Pipelines** page, click a pipeline name to open the pipeline editor.

4. Click **Add Cell** > **Python**.

5. Click the cell name and enter a name for the cell.

6. Add your Python code to the cell body.

## Run a Python cell

See [Run cells in the Astro Cloud IDE](run-cells.md).

## Create explicit dependencies for a Python cell

In a Python cell, click **Dependencies** and select a cell to make it an explicit upstream dependency of your Python cell. When you run your entire pipeline, the Python cell cannot begin running until the selected upstream cell finishes running.

To make a Python cell an upstream dependency for another cell, click **Dependencies** for the other cell and select the name of your Python cell. 

## Create data dependencies for a Python cell

You can use the output of other cells in your project within a Python function. You define these dependencies in Python, and the Cloud IDE automatically renders the dependencies in your project code and in the **Pipeline** view of your project.

### Pass a value from one Python cell to another Python cell 

Use the value of a Python cell's `return` statement in another Python cell by calling the name of the Python cell containing the `return` statement. Doing this automatically creates a dependency between the cells.

For example, consider two Python cells. One cell is named `hello_world` and includes the following code:

```sh
return "Hello, world!"
```

Another cell is named `data_dependency` and includes the following code:

```sh
my_string = hello_world
return my_string
```

The **Pipeline** view in the Cloud IDE shows the newly created dependency between these two cells. 

![New dependency graph](/img/cloud-ide/data-dependency.png)

### Pass a value from a SQL cell to a Python cell 

Use the results of a SQL cell in your Python cell by calling the name of the SQL cell. The SQL cell must contain a `SELECT` statement. 

The table created by the `SELECT` statement is automatically converted to pandas DataFrame and passed to the Python cell.

The following Python cell is dependent on a SQL cell named `my_sql_cell`.

```python
df = my_sql_cell # my_sql_cell is a SQL cell which gets converted to a pandas DataFrame by default
df['col_a'] = df['col_a'] + 1
return df
```

## View complete code for Python cells

To view your Python cell within the context of an Airflow DAG, click **Code**. The Airflow DAG includes your Python function as well as all of the code required to run it on Airflow.

All Python cells execute Python using `aql.dataframe`, which is a function available in the Astro SDK. See [Astro SDK documentation](https://astro-sdk-python.readthedocs.io/en/stable/astro/sql/operators/dataframe.html).

## See also

- [Run cells in the Astro Cloud IDE](cloud-ide/run-cells.md).