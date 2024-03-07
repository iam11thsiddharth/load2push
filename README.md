<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Load2Push</title>
</head>
<body>
    <h1>Load2Push</h1>

    <p>This Cloudflare Worker script interacts with the Baserow API to fetch row data from a specified table and insert data into another table. It also includes a feature to fetch the current user's IP address and send it to a designated column in the Baserow table.</p>

    <h2>Usage</h2>

    <ol>
        <li>Clone this repository:</li>
    </ol>

    <pre><code>git clone https://github.com/iam11thsiddharth/load2push.git</code></pre>

    <ol start="2">
        <li>Install dependencies (none required for Cloudflare Workers).</li>
        <li>Deploy the Cloudflare Worker to your Cloudflare account using the <a href="https://dash.cloudflare.com/">Cloudflare Workers dashboard</a>.</li>
        <li>Configure the necessary environment variables:</li>
    </ol>

    <ul>
        <li><code>BASEROW_API_KEY</code>: Your Baserow API key.</li>
        <li><code>BASEROW_TABLE_ID</code>: The ID of the Baserow table where data will be inserted.</li>
        <li>(Optional) <code>BASEROW_ROW_ID</code>: The ID of the Baserow row to fetch data from.</li>
    </ul>

    <ol start="5">
        <li>Use the Cloudflare Worker URL in your applications to fetch and insert data from/to Baserow.</li>
    </ol>

    <h3>Features</h3>

    <ul>
        <li>Fetches full row data from Baserow using the provided row ID.</li>
        <li>Inserts data into a specified table in Baserow using POST requests.</li>
        <li>Optionally fetches the current user's IP address and sends it to a designated column in the Baserow table if requested.</li>
    </ul>

    <h4>Example Usage</h4>

    <p>To fetch row data from Baserow:</p>

    <pre><code>https://your-worker-url.example.com?id=123</code></pre>

    <p>To insert data into Baserow:</p>

    <pre><code>https://your-worker-url.example.com?id=123&amp;param1=value1&amp;param2=value2</code></pre>

    <p>To fetch the current user's IP and insert it into Baserow:</p>

    <pre><code>https://your-worker-url.example.com?id=123&amp;ip=yes&amp;param1=value1&amp;param2=value2</code></pre>

    <p><strong>Note:</strong></p>

    <ul>
        <li>You can use <code>ip=yes</code> parameter to store the IP address of the user in your table (a column named - <code>ip</code> must exist).</li>
        <li>Parameter names must be exactly the same as your Baserow table's column names.</li>
        <li>Avoid using capital alphabets in your database table/column/row or parameters and others.</li>
    </ul>

    <h5>Credits</h5>

    <p>This Cloudflare Worker script was developed by <a href="https://github.com/iam11thsiddharth">Siddharth</a>.</p>

    <h6>License</h6>

    <p>This project is licensed under the MIT License - see the <a href="LICENSE">LICENSE</a> file for details.</p>
</body>
</html>
