<h1 style="color: #4A90E2; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; background-color: #E6F0FA; padding: 15px; border-radius: 10px;">
    Task 7: Get Basic Sales Summary from a Tiny SQLite Database using Python
</h1>

<h2 style="color: #2C3E50; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">🎯 Objective</h2>
<p style="font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; color: #34495E;">
    Use SQL inside Python to pull simple sales info (like total quantity sold, total revenue), and display it using basic <code style="background-color: #ECF0F1; padding: 3px 6px; border-radius: 5px;">print()</code> statements and a simple bar chart.
</p>

<h2 style="color: #2C3E50; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">🛠 Tools</h2>
<ul style="font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; color: #2D3436; list-style-type: circle; padding-left: 20px;">
    <li style="color: #1ABC9C;">Python (with <code>sqlite3</code>, <code>pandas</code>, <code>matplotlib</code>)</li>
    <li style="color: #1ABC9C;">SQLite (built into Python — no setup!)</li>
    <li style="color: #1ABC9C;">Jupyter Notebook or a .py file</li>
</ul>

<h2 style="color: #2C3E50; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">📦 Dataset</h2>
<p style="font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; color: #34495E;">
    Create a small SQLite database file named <code style="background-color: #ECF0F1; padding: 3px 6px; border-radius: 5px;">sales_data.db</code> with a single table called <code style="background-color: #ECF0F1; padding: 3px 6px; border-radius: 5px;">sales</code> having columns: <code>id</code>, <code>product</code>, <code>quantity</code>, <code>price</code>, and <code>sale_date</code> (YYYY-MM-DD).
</p>

<h2 style="color: #2C3E50; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">🎁 Deliverables</h2>
<ul style="font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; color: #2D3436; list-style-type: square; padding-left: 20px;">
    <li>Python script (.py) or Jupyter Notebook (.ipynb) that:</li>
    <ul style="list-style-type: disc; padding-left: 40px;">
        <li>Connects to <code>sales_data.db</code></li>
        <li>Runs 1–2 SQL queries</li>
        <li>Displays output using <code>print()</code></li>
        <li>Plots a bar chart with <code>matplotlib</code> and saves it as <code>sales_chart.png</code></li>
    </ul>
</ul>

<h2 style="color: #2C3E50; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">💡 Hints / Mini Guide</h2>
<div style="background-color: #FDF2E9; border-left: 6px solid #E67E22; padding: 15px; margin: 10px 0; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">
    <h3 style="color: #D35400;">Python & SQLite Essentials</h3>
    <ul style="padding-left: 20px;">
        <li>Load SQLite database:<br>
            <code style="background-color: #ECF0F1; padding: 3px 6px; border-radius: 5px; display: block;">import sqlite3<br>conn = sqlite3.connect("sales_data.db")</code>
        </li>
        <li>Run SQL query:<br>
            <code style="background-color: #ECF0F1; padding: 3px 6px; border-radius: 5px; display: block;">query = "SELECT product, SUM(quantity) AS total_qty, SUM(quantity * price) AS revenue FROM sales GROUP BY product"</code>
        </li>
        <li>Load into pandas:<br>
            <code style="background-color: #ECF0F1; padding: 3px 6px; border-radius: 5px; display: block;">import pandas as pd<br>df = pd.read_sql_query(query, conn)</code>
        </li>
        <li>Print results:<br>
            <code style="background-color: #ECF0F1; padding: 3px 6px; border-radius: 5px; display: block;">print(df)</code>
        </li>
        <li>Plot bar chart:<br>
            <code style="background-color: #ECF0F1; padding: 3px 6px; border-radius: 5px; display: block;">df.plot(kind='bar', x='product', y='revenue')<br>plt.savefig("sales_chart.png")</code>
        </li>
        <li>Close connection:<br>
            <code style="background-color: #ECF0F1; padding: 3px 6px; border-radius: 5px; display: block;">conn.close()</code>
        </li>
    </ul>
</div>
