from Mohamedapi import MohamedAPI
from Mohamedapi.responses import JSONResponse

app = MohamedAPI()

@app.get("/about")
async def about():
    return JSONResponse(content={
        "fullName": "Mohamed",
        "role": "Developer / Builder",
        "focus": [
            "automation",
            "web development",
            "AI tooling",
            "data extraction",
            "trading systems"
        ],
        "interests": [
            "programming",
            "anime",
            "manhwa",
            "technology",
            "financial markets"
        ],
        "skills": [
            "Python",
            "JavaScript",
            "Node.js",
            "web scraping",
            "OCR pipelines",
            "API integration",
            "automation scripting"
        ],
        "currentProjects": [
            "AI OCR pipeline for manhwa translation",
            "custom manga/manhwa website infrastructure",
            "automation tools for data extraction",
            "trading research systems"
        ]
    })

@app.get("/contact")
async def contact():
    return JSONResponse(content={
        "message": "Contact endpoint intentionally minimal.",
        "note": "No personal contact information exposed."
    })

@app.exception_handler(404)
async def not_found(request, exc):
    return JSONResponse(
        content={"message": "Endpoint does not exist"},
        status_code=404
    )
