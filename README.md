Paradigm PDF Analyzer | Professional Edition
============================================

**Paradigm** is a client-side, browser-based PDF analysis tool designed for semantic field detection, layout estimation, and form digitization. It runs entirely in the browser using WebAssembly (via PDF.js) and requires no backend server.

?? Features
-----------

### ?? Semantic Intelligence

-   **Deep Layout Engine**: distinguishing between vector geometry (lines/boxes) and text nodes.

-   **Semantic Estimator**: Automatically predicts field types (e.g., `NAME`, `ADDRESS`, `DATE`, `SSN`) based on label context.

-   **Smart Context**: Links underscore lines (`______`) to their preceding text labels.

### ??? Interface & Visualization

-   **HUD Visualizer**: Overlays detected fields and metadata directly onto the PDF canvas.

-   **Tactical Filmstrip**: Bottom-docked thumbnail navigation with "Sync Lock" to keep your place.

-   **Auto-Fit Engine**: Automatically scales the document to fit your viewport.

-   **Touch & Swipe**: Native touch support for navigating pages on mobile/tablet devices.

### ?? Data & Export

-   **Page Intel**: Live metrics on page dimensions, permissions, and text density.

-   **OpenAPI Spec**: Generates a Swagger/OpenAPI 3.0 definition for the data structure.

-   **JSON Data Stream**: Full access to the raw analysis payload (Fields, Vectors, Text, Layout).

??? Quick Start
---------------

### Option 1: Run Locally

1.  Clone this repository.

2.  Open `analyzer.html` in any modern web browser (Chrome, Firefox, Edge, Safari).

3.  Drag and drop a PDF to begin analysis.

### Option 2: Host on GitHub Pages

1.  Fork this repository.

2.  Go to **Settings** > **Pages**.

3.  Set the source branch to `main` (or `master`) and save.

4.  Your analyzer will be live at `https://<your-username>.github.io/<repo-name>/analyzer.html`.

?? Data Payload Structure
-------------------------

The analyzer outputs a structured JSON payload organized by page:

```
{
  "meta": {
    "avgLineHeight": 14.5,
    "margins": { "top": 50, "bottom": 750, "left": 40, "right": 550 }
  },
  "pages": [
    {
      "page_number": 1,
      "fields": [
        {
          "key": "Full Name",
          "prediction": "NAME",
          "source": "Underscore",
          "rect": { "x": 100, "y": 600, "w": 200, "h": 15 }
        }
      ],
      "vectors": [...],
      "text_content": [...]
    }
  ]
}

```

??? Tech Stack
--------------

-   **Core**: HTML5, Vanilla JavaScript (ES6+)

-   **PDF Parsing**: [PDF.js](https://mozilla.github.io/pdf.js/ "null") (v3.11.174)

-   **Styling**: Tailwind CSS (CDN)

-   **Icons**: Lucide Icons

-   **Fonts**: Inter (Google Fonts)

?? License
----------

This project is open-source and available under the [MIT License](https://www.google.com/search?q=LICENSE "null").
