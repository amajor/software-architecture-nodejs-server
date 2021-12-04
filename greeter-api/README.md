# Greeter API

Copy and paste the [gretter-api-specs.yaml](./greeter-api-specs.yaml) file 
into the [Swagger Editor](https://editor.swagger.io/).

![Greeter YAML in Editor](../docs/images/Greeter%20in%20Editor.png)

Do the following and include in the [deliverables](../DELIVERABLES.md).

## OPTIONAL DELIVERABLES

### Step 1

Add `limit` query parameter to the `/greetings` GET endpoint, 
where `limit` is an integer value and represents the maximum number of greetings 
that can be returned by the endpoint.

### Step 2

As per specification, the only currently possible response for `/greetings` POST endpoint is 200/success, add another possible response of 500/server-error along with a new Error schema consisting of the following fields:

  - `code`: an integer with two possible values: 1000, 2000
  - `message`: a string with two possible values: `“server is too busy”`, `“greeting already exists”`