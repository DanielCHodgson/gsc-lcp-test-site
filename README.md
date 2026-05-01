<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />

  <title>GSC LCP Plugin Test Site</title>

  <meta
    name="description"
    content="Test harness for shaping Google Search Console API requests and responses before building a SquaredUp low-code plugin."
  />

  <link rel="stylesheet" href="./styles.css" />
</head>

<body>

<header class="site-header">
  <div class="container">

    <p class="eyebrow">
      SquaredUp low-code plugin testing
    </p>

    <h1>
      Google Search Console API tester
    </h1>

    <p class="lede">
      Use this page to prototype Search Console requests and preview how results
      should be flattened for SquaredUp custom data streams.
    </p>

  </div>
</header>


<main class="layout container">

  <section class="card">

    <h2>Request configuration</h2>

    <label for="siteUrl">
      Site URL (must match Search Console property)
    </label>

    <input
      id="siteUrl"
      type="text"
      value="https://example.com/"
    />


    <label for="startDate">
      Start date
    </label>

    <input
      id="startDate"
      type="date"
    />


    <label for="endDate">
      End date
    </label>

    <input
      id="endDate"
      type="date"
    />


    <label for="dimensions">
      Dimensions
    </label>

    <select
      id="dimensions"
      multiple
    >
      <option value="date" selected>Date</option>
      <option value="query">Query</option>
      <option value="page">Page</option>
      <option value="country">Country</option>
      <option value="device">Device</option>
      <option value="searchAppearance">Search appearance</option>
    </select>


    <label for="rowLimit">
      Row limit
    </label>

    <input
      id="rowLimit"
      type="number"
      value="1000"
      min="1"
      max="25000"
    />


    <div class="button-row">

      <button id="buildRequestBtn">
        Build request body
      </button>

      <button
        id="mockResponseBtn"
        class="secondary"
      >
        Load mock response
      </button>

    </div>

  </section>


  <section class="card">

    <h2>
      Generated request
    </h2>

    <p class="hint">
      POST /webmasters/v3/sites/{siteUrl}/searchAnalytics/query
    </p>

    <pre
      id="requestOutput"
      class="output"
    >
{}
    </pre>

  </section>


  <section class="card wide">

    <h2>
      SquaredUp-friendly rows
    </h2>

    <p class="hint">
      Flattened rows suitable for tile usage or indexing streams
    </p>

    <div class="table-wrap">

      <table>

        <thead>
          <tr>
            <th>Date</th>
            <th>Query</th>
            <th>Page</th>
            <th>Clicks</th>
            <th>Impressions</th>
            <th>CTR</th>
            <th>Position</th>
          </tr>
        </thead>

        <tbody id="rowsOutput">

          <tr>
            <td colspan="7" class="empty">
              No data yet — build request or load mock response
            </td>
          </tr>

        </tbody>

      </table>

    </div>

  </section>



  <section class="card wide">

    <h2>
      Raw response preview
    </h2>

    <pre
      id="rawOutput"
      class="output"
    >
{}
    </pre>

  </section>


</main>


<footer class="site-footer container">

  <p>
    Static GitHub Pages test harness — do not store OAuth secrets here.
  </p>

</footer>


<script src="./script.js"></script>

</body>
</html>