GoEverywhere Rural Transportation Application
=============================================

Overview
--------

The GoEverywhere application is a dial‑a‑ride (DAR) solution aimed at improving rural transportation by optimizing ride routes using Google OR‑Tools. Our project is designed around three distinct case studies that differ in the number of ride requests, available vehicles, and geographic region size. This approach enables us to research how the system scales and how accessibility constraints (bike and wheelchair requests) affect performance.

### Case Study Descriptions

-   **Case Study A (Small Region):**

    -   **Configuration:** 10 requests, 2 vehicles, region size ±0.05°

    -   **Focus:** Examine performance with a low number of requests over a small area.

-   **Case Study B (Moderate Region):**

    -   **Configuration:** 20 requests, 4 vehicles, region size ±0.1°

    -   **Focus:** Understand system behavior under typical conditions.

-   **Case Study C (Large Region):**

    -   **Configuration:** 30 requests, 6 vehicles, region size ±0.2°

    -   **Focus:** Stress test the algorithm with high demand and greater geographic spread.

For each scenario, the application randomly assigns ride pickup/dropoff locations and accessibility requirements, and vehicles are randomly designated as bike- and/or wheelchair-accessible.

What the Results Show
---------------------

Our analysis includes several charts:

-   **Distance per Vehicle:** Displays how the total route distance is distributed among vehicles.

-   **Stops per Vehicle:** Shows the number of pickups/dropoffs per vehicle, indicating load balance.

-   **Accessibility Demand vs. Supply:** Compares the number of accessibility requests to the number of vehicles equipped to handle them.

-   **Distribution of Route Segment Distances:** Highlights the lengths of individual route segments, revealing if rides are mostly short or if some are very long.

-   **Load Over Route Order:** Illustrates how each vehicle's passenger load changes at each stop.

In addition, our Folium maps display the computed routes and, where possible, include turn‑by‑turn directions extracted via OSMnx (with a fallback to straight‑line paths if no route is found).

How to Reproduce
----------------

To reproduce the results, follow these steps:

1.  **Install Anaconda Navigator:**\
    If you haven't already, download and install Anaconda Navigator.

2.  **Open Anaconda Navigator and Launch JupyterLab:**

    -   Open Anaconda Navigator.

    -   Click the "Launch" button under **JupyterLab**.

3.  **Open the Notebook:**

    -   In JupyterLab, navigate to the folder containing the file **`DARP_LATEST.ipynb`**.

    -   Click to open the notebook.

4.  **Install Required Libraries:**\
    Ensure you have the following Python packages installed. You can install them via Anaconda Prompt or within a Jupyter cell:

    bash

    Copy

    `pip install ortools folium osmnx networkx haversine pandas matplotlib`

    (If using conda, you might also use `conda install` where available.)

5.  **Run All Cells:**

    -   In JupyterLab, select **Run > Run All Cells** (or press Shift+Enter repeatedly).

    -   The notebook will generate three distinct case studies, compute optimized routes, and create charts with descriptive explanations.

    -   The Folium maps (saved as HTML files) are also generated and can be viewed inline.

6.  **Review the Output:**

    -   The notebook will print aggregated metrics for each scenario.

    -   Multiple charts will be displayed, along with textual explanations of what each chart shows.

    -   A results page (`results.html`) will be generated that summarizes the key metrics and provides links to the route maps.

Summary
-------

This project demonstrates a scalable, accessible DAR solution for rural areas by analyzing three different scenarios. Our research focuses on:

-   How route distance and simulation time scale with increased demand and area size.

-   The balance of workload among vehicles.

-   Whether the system's accessibility features meet the demands of riders.

-   How individual route segments contribute to overall performance.

By following the above steps, you can reproduce our experiments and explore the detailed analytics provided in the notebook.