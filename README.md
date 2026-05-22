# AI Tip of the Day

A web page that fetches a random fact from a live API and displays it. Click "New Fact" and a fresh one appears every time.

## How it works

When the page loads (and each time you press the button), a function called `fetchFact()` runs. It reaches out to the API over the internet, waits for a response, pulls the fact out of the data, and writes it into the card. The `async/await` pattern handles the waiting, and a `try/catch` block handles anything that goes wrong.

## What clicked for me

- **Calling an API**: `fetch()` sends the request, `.json()` parses the response, and then you use the data however you want.
- **Error handling**: `try/catch` prevents the page from breaking if the API went down. The user will see a clear message instead of a blank screen if the page breaks.
- **Responsive design**: using media queries allows the page to adjust its layout for smaller screens
