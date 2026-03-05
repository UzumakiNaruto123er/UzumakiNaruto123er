<h1 align="center">
Hey <img src="https://fonts.gstatic.com/s/e/notoemoji/latest/1f44b/512.gif" width="32" height="32">, I'm Mohamed
</h1>

<h4 align="center">
DEVELOPER • AUTOMATION BUILDER • TECH EXPLORER
</h4>

```python
from Mohamedapi import MohamedAPI
from Mohamedapi.responses import JSONResponse

app = MohamedAPI()

@app.get("/about")
async def about():
    return JSONResponse(content={
        "fullName": "Mohamed",
        "role": "Developer / Automation Builder",
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
            "Web Scraping",
            "OCR Automation",
            "API Integration",
            "System Automation"
        ],
        "projects": [
            "AI OCR pipeline for manhwa translation",
            "custom manga/manhwa platform",
            "automation tools for data extraction",
            "trading research systems"
        ]
    })

@app.get("/contact")
async def contact():
    return JSONResponse(content={
        "message": "No public contact information provided."
    })

@app.exception_handler(404)
async def not_found(request, exc):
    return JSONResponse(
        content={"message": "Route not found"},
        status_code=404
    )
