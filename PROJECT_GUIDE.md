# Rural dial-a-ride optimization

This 2025 academic project explores routing with Google OR-Tools, OpenStreetMap road networks through OSMnx, and synthetic rider requests with bike/wheelchair accessibility requirements. The existing README contains the original analysis and charts.

## Recommended entry point

Use the root **`DARP_LATEST.ipynb`** as the main notebook. `Algorithms/` contains earlier experimental versions; these are retained for provenance, not separate recommended entry points. `Maps/` and `images/` contain saved study artifacts.

Install the dependencies listed in `requirements.txt` in a separate environment, open the notebook in Jupyter, and run its cells in order. Map downloads require internet access. This cleanup has not rerun the optimization or validated a locked dependency environment.

## Interpreting the results

- Road networks are real; rider locations and accessibility demands are simulated.
- The notebook sets vehicle capacities to 9999 to isolate other effects. Passenger loads in the saved charts therefore do not establish real-world fleet feasibility.
- Demand and vehicle capabilities use randomized inputs. For a repeatable new experiment, set both `random.seed(42)` and `np.random.seed(42)` after imports and before generating data, and record dependency versions and the map snapshot.
- Saved charts describe historical runs; they are not evidence of measured production performance or model-grading accuracy.

The study is useful as an example of constraint modeling, scenario analysis, visualization, and examining a solver's limitations. It complements the [Android/backend application](https://github.com/paulvan2000/go-everywhere).
