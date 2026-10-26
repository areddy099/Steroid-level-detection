# MilkGuard – Flask + SQLite backend
    pip install -r requirements.txt
    python app.py        # open http://127.0.0.1:5000

The dashboard in `static/index.html` detects the API and switches from browser storage to the database.

| Endpoint | Purpose |
|---|---|
| GET /api/samples?farm=&hormone=&status=&batch=&days= | filtered samples |
| POST /api/samples | add one sample (JSON: date, farm, hormone, concentration, method, temp, batch) |
| POST /api/upload | CSV upload (form field `file`, columns date,farm,hormone,concentration,method,temp,batch) |
| GET /api/trend?hormone= | daily average % of limit |
| GET /api/batches · PATCH /api/batches/<id> | batch status; release is blocked if any sample is a violation |

Limits in `LIMITS` are illustrative: set them from your regulator before real use.
