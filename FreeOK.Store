<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>FreeplayOK – Oklahoma Casino Free Play & Rewards</title>
  <meta name="description" content="Discover Oklahoma casino free play rewards, promotions, and daily treasure hunt prizes." />
  <meta name="viewport" content="width=device-width, initial-scale=1" />

  <!-- SEO -->
  <link rel="canonical" href="https://freeplayok.com" />

  <!-- Tailwind -->
  <script src="https://cdn.tailwindcss.com"></script>

  <!-- React -->
  <script src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
  <script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>

  <!-- PWA -->
  <link rel="manifest" href="manifest.json">
  <meta name="theme-color" content="#facc15">

  <!-- Schema -->
  <script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "WebSite",
    "name": "FreeplayOK",
    "url": "https://freeplayok.com",
    "potentialAction": {
      "@type": "SearchAction",
      "target": "https://freeplayok.com/?q={search_term_string}",
      "query-input": "required name=search_term_string"
    }
  }
  </script>
</head>

<body class="bg-gray-50 text-gray-900">
  <div id="root"></div>

<script>
const { useState } = React;

function App() {
  const casinos = [
    { name: "River Spirit Casino", city: "Tulsa", slug: "riverspirit" },
    { name: "Choctaw Casino", city: "Durant", slug: "choctaw" },
    { name: "Hard Rock Casino", city: "Tulsa", slug: "hardrock" }
  ];

  const [query, setQuery] = useState("");
  const [treasure, setTreasure] = useState(null);

  const filtered = casinos.filter(c =>
    (c.name + c.city).toLowerCase().includes(query.toLowerCase())
  );

  function affiliateUrl(slug) {
    return `https://partner.example.com/${slug}?ref=freeplayok&utm_source=affiliate&utm_campaign=oklahoma`;
  }

  function huntTreasure() {
    const today = new Date().toDateString();
    const last = localStorage.getItem("treasurePlayed");

    if (last === today) {
      setTreasure("Come back tomorrow for another hunt!");
      return;
    }

    localStorage.setItem("treasurePlayed", today);
    const prizes = ["$5 Free Play", "$10 Free Play", "$25 Free Play", "No luck this time"];
    setTreasure(prizes[Math.floor(Math.random() * prizes.length)]);
  }

  return (
    React.createElement("div", { className: "min-h-screen flex flex-col" },

      /* Header */
      React.createElement("header", { className: "bg-white shadow p-4 flex justify-between" },
        React.createElement("h1", { className: "text-2xl font-bold" }, "FreeplayOK"),
        React.createElement("span", { className: "text-sm text-gray-600 hidden md:block" },
          "Oklahoma Casino Free Play"
        )
      ),

      /* Hero */
      React.createElement("section", { className: "bg-yellow-100 text-center p-10" },
        React.createElement("h2", { className: "text-3xl font-bold mb-4" },
          "Discover Free Play Rewards at Oklahoma Casinos"
        ),
        React.createElement("p", { className: "mb-6 text-gray-700" },
          "Verified casinos • Updated daily • No credit card required"
        ),
        React.createElement("input", {
          className: "border p-3 w-full max-w-xl mx-auto rounded",
          placeholder: "Search casinos or cities...",
          onChange: e => setQuery(e.target.value)
        })
      ),

      /* Casino Results */
      React.createElement("main", { className: "p-6 grid gap-6 md:grid-cols-2 lg:grid-cols-3 flex-grow" },
        filtered.map(c =>
          React.createElement("div", {
            key: c.name,
            className: "bg-white p-4 rounded shadow"
          },
            React.createElement("h3", { className: "font-semibold text-lg" }, c.name),
            React.createElement("p", { className: "text-sm text-gray-600" }, c.city),
            React.createElement("a", {
              href: affiliateUrl(c.slug),
              target: "_blank",
              rel: "nofollow sponsored",
              className: "block mt-4 bg-yellow-400 text-center py-2 rounded font-semibold"
            }, "Claim Free Play")
          )
        )
      ),

      /* Treasure Hunt */
      React.createElement("section", { className: "bg-white p-6 text-center shadow" },
        React.createElement("h3", { className: "text-xl font-bold mb-3" }, "🎁 Daily Treasure Hunt"),
        React.createElement("button", {
          onClick: huntTreasure,
          className: "bg-green-600 text-white px-6 py-2 rounded"
        }, "Hunt for Treasure"),
        treasure && React.createElement("p", { className: "mt-4 font-semibold" }, treasure)
      ),

      /* Footer */
      React.createElement("footer", { className: "bg-white text-center p-4 text-xs text-gray-600 mt-6" },
        React.createElement("p", null, "© 2025 FreeplayOK. All rights reserved."),
        React.createElement("p", null, "Must be 21+. Play responsibly."),
        React.createElement("p", null, "Disclosure: We may earn a commission from partner links.")
      )
    )
  );
}

ReactDOM.createRoot(document.getElementById("root"))
  .render(React.createElement(App));
</script>

</body>
</html>
