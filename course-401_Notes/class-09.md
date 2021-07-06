# HTTP requests : 

* HttpUrlConnection : 
HttpURLConnection class is an abstract class directly extending from URLConnection class. It includes all the functionality of its parent class with additional HTTP specific features. HttpsURLConnection is another class which is used for the more secured HTTPS protocol.

* Creating a Request : 
to initiate a HttpUrlConnection instance , we should use openConnection() method of URL class , but we still didn't establish the connection . 

Example :

        URL url = new URL("http://example.com");
        HttpURLConnection con = (HttpURLConnection) url.openConnection();
        con.setRequestMethod("GET");


* Adding Request Parameters : 

to add parameters to a request , we have to set the doOutput to true .

Example : 

        Map<String, String> parameters = new HashMap<>();
        parameters.put("param1", "val");

        con.setDoOutput(true);
        DataOutputStream out = new DataOutputStream(con.getOutputStream());
        out.writeBytes(ParameterStringBuilder.getParamsString(parameters));
        out.flush();
        out.close();

* Setting Request Headers : 
we can set the headers for a request using setRequestProperty() method  . 

Example :

        con.setRequestProperty("Content-Type", "application/json");

and we can read it , using getRequestProperty 

Example :

        String contentType = con.getHeaderField("Content-Type");

* Configuring Timeouts  : 
connect timeout is the interval time to wait for the connection to the server to be established .
read timeout is the interval time to wait for the data to be available for reading .
we can set them using setConnectTimeout , setReadTimeout methods .
Example : 

        con.setConnectTimeout(5000);
        con.setReadTimeout(5000);


* Reading the Response :
to read the response for our request , we should parse the inputStream of the HttpUrlConnection instance . 

Example : 

        BufferedReader in = new BufferedReader(
          new InputStreamReader(con.getInputStream()));
        String inputLine;
        StringBuffer content = new StringBuffer();
        while ((inputLine = in.readLine()) != null) {
            content.append(inputLine);
        }
        in.close();

        con.disconnect();  //to close the connection 

