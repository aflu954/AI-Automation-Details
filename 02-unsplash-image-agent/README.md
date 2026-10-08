Unsplash Image Agent (n8n)
Objective
Build a simple Image Agent using n8n that accepts a keyword as input and returns 3 image URLs from the Unsplash API.

1. Webhook Setup (Input)
Configure a Webhook node with the following settings:

Method: GET

The workflow should accept a query parameter, for example:

?q=coffee
2. Unsplash API Integration
Add an HTTP Request node with the following configuration:

Method:

GET
URL:

https://api.unsplash.com/search/photos 
Add the following query parameters:
query → {{$json.query.q}}

per_page → 3

Add the following header:

Authorization → Client ID YOUR_UNSPLASH_ACCESS_KEY

3. Process Image Data

Add a Set node.

Keep only one field:

images = {{$json.results.map(r => r.urls.full)}}

4. Return the Response
Add a Respond to Webhook node.

Return the images field as the JSON response.

Expected Output
{
  "images": [
    "url1",
    "url2",
    "url3"
  ]
}
Details:
●Screenshot of the complete workflow

●One test URL (Webhook URL with query)

●Output JSON response
