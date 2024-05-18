# How-Web-Works-Exercise
1. **HTTP (Hypertext Transfer Protocol)**: It's a set of rules for transferring data over the internet. It enables web browsers to request and receive web pages and other resources from web servers.

2. **URL (Uniform Resource Locator)**: It's the address of a specific resource on the internet. URLs specify the protocol to be used (like HTTP or HTTPS), the domain name, and the path to the resource.

3. **DNS (Domain Name System)**: It's like a phone book for the internet, translating human-readable domain names into IP addresses that computers use to communicate. DNS servers match domain names to their corresponding IP addresses, enabling users to access websites using familiar names instead of numeric IP addresses.

4. **Query String**: It's a part of a URL containing data sent to a web server as parameters. It's typically used for passing information like search terms or user inputs to the server.

5. **HTTP Verbs**: They are actions used to perform different operations on resources. `GET` retrieves data from a server, while `POST` submits data to be processed or stored on the server.

6. **HTTP Request**: It's a message sent from a client to a server, asking for a specific action or resource. It includes information like the URL, HTTP method, and optional data.

7. **HTTP Response**: It's a message sent from a server to a client in reply to an HTTP request. It contains the requested resource along with additional metadata like response status and headers.

8. **HTTP Header**: It's additional information sent along with HTTP requests and responses. Headers provide details such as content type, caching instructions, and client/browser information.

9. **Process of Typing a URL into a Browser**: When you type a URL into a browser, the browser checks if it's valid, translates the domain name to an IP address using DNS, sends an HTTP request to the server specified in the URL, and receives an HTTP response containing the requested web page.

Part Two: Practice Tools
Using curl, make a GET request to the icanhazdadjoke.com API to find all jokes involving the word “pirate”.
curl -X GET "https://icanhazdadjoke.com/search?term=pirate" -H "Accept: application/json"
"https://icanhazdadjoke.com/search?term=pirate" -H "Accept: application/json"
{"current_page":1,"limit":20,"next_page":1,"previous_page":1,"results":[{"id":"2gii3LeN7Ed","joke":"Why couldn't the kid see the pirate movie? Because it was rated arrr!"},{"id":"SvzIBAQS0Dd","joke":"What did the pirate say on his 80th birthday? Aye Matey!"},{"id":"QuscibaMClb","joke":"What does a pirate pay for his corn? A buccaneer!"},{"id":"exXSCtkOKe","joke":"Why do pirates not know the alphabet? They always get stuck at \"C\"."},{"id":"SnOf2gqjiqc","joke":"Why are pirates called pirates? Because they arrr!"}],"search_term":"pirate","status":200,"total_jokes":5,"total_pages":1}


Use dig to find what the IP address is for icanhazdadjoke.com?
dig +short icanhazdadjoke.com
104.21.16.216
172.67.187.189

Make a simple web page and serve it using python3 -m http.server. Visit the page in a browser.
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Simple Web Page</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f0f0f0;
      color: #333;
      margin: 0;
      padding: 0;
    }

    header {
      background-color: #333;
      color: #fff;
      padding: 10px 0;
      text-align: center;
    }

    h1 {
      margin-top: 20px;
      text-align: center;
    }

    p {
      text-align: center;
    }
  </style>
</head>
<body>
  <header>
    <h1>Welcome to My Simple Web Page</h1>
  </header>
  
  <main>
    <h2>Basic HTML Elements</h2>
    <p>This is my simple web page that has been created using python3 -m http.server.</p>
    
    <h3>Link Example</h3>
    <a href="https://www.SimpleWebPage.com">Visit Example Website</a>
  </main>
  
  <footer>
    <p>&copy; 2024 Simple Web Page. All rights reserved.</p>
  </footer>
</body>
</html>

Part Three: Explore Dev Tools

Build a very simple HTML form that uses the GET method (it can use the same page URL for the action) when the form is submitted.
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Simple Form</title>
</head>
<body>

  <h2>Simple Form</h2>

  <form action="" method="GET">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required>
    <br><br>
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required>
    <br><br>
    <button type="submit">Submit</button>
  </form>

</body>
</html>

Add a field or two to the form and, after submitting it, explore in Chrome Developer tools how you can view the request and response headers.

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Simple Form</title>
</head>
<body>

  <h2>Simple Form</h2>

  <form action="" method="GET">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required>
    <br><br>
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required>
    <br><br>
    <label for="age">Age:</label>
    <input type="number" id="age" name="age" required>
    <br><br>
    <button type="submit">Submit</button>
  </form>

</body>
</html>

Edit the page to change the form type to POST, refresh in the browser and re-submit. Do you still see the field in the query string? Explore in Chrome how you can view the request and response headers, as well as the form data.
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Simple Form</title>
</head>
<body>

  <h2>Simple Form</h2>

  <form action="" method="POST">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required>
    <br><br>
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required>
    <br><br>
    <label for="age">Age:</label>
    <input type="number" id="age" name="age" required>
    <br><br>
    <button type="submit">Submit</button>
  </form>

</body>
</html>

Part Four: Explore the URL API

const urlString = 'https://example.com/path?query=value#fragment';
const url = new URL(urlString);
console.log(url);

console.log('Protocol:', url.protocol); // "https:"
console.log('Host:', url.host); // "example.com"
console.log('Path:', url.pathname); // "/path"
console.log('Query string:', url.search); // "?query=value"
console.log('Hash fragment:', url.hash); // "#fragment"

const params = new URLSearchParams(url.search);
console.log('Query parameters:');
for (const [key, value] of params) {
    console.log(key, '=', value);
}

url.hash = 'new-fragment';
console.log('Modified URL:', url.href); // "https://example.com/path?query=value#new-fragment"

params.append('newParam', 'newValue');
url.search = params.toString();
console.log('Modified URL with new query parameter:', url.href); // "https://example.com/path?query=value&newParam=newValue#new-fragment"




