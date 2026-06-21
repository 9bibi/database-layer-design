## Project overview

A simple fracture detection system: users upload an X-ray, the backend
runs it through a deep learning model, and returns a prediction
(fracture / review needed / no fracture) along with a heatmap showing
which region influenced the result.

## Architecture

This project follows the **MVC (Model-View-Controller)** pattern:

- **Model** — the database layer (patients, scans, predictions, heatmaps)
  and the prediction logic (the trained model, heatmap generation).
- **View** — the web frontend that displays the upload form, the prediction
  result, and the heatmap overlay.
- **Controller** — the FastAPI route handlers (e.g. `POST /predict`) that
  receive requests, call the Model, and pass the result to the View.

MVC was chosen because it cleanly separates the data and prediction logic
from the user interface. This makes it easy to update the model or the
database schema without touching how results are displayed, and the other
way around.
