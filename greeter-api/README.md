# Greeter API

Copy and paste the [gretter-api-specs.yaml](./greeter-api-specs.yaml) file 
into the [Swagger Editor](https://editor.swagger.io/).

![Greeter YAML in Editor](../docs/images/Greeter%20in%20Editor.png)

Do the following and include in the [deliverables](../DELIVERABLES.md).
See the completed solution in the 
[gretter-api-updated.yaml](./greeter-api-updated.yaml) file.

## OPTIONAL DELIVERABLES

### Step 1

Add `limit` query parameter to the `/greetings` GET endpoint, 
where `limit` is an integer value and represents the maximum number of greetings 
that can be returned by the endpoint.

#### Solution

Look at the query parameter documentation at 
https://swagger.io/docs/specification/describing-parameters/#query-parameters

Add this to the `/greetings` GET path command.

```yaml
      parameters:
      - in: query
        name: limit
        type: integer
        description: The maximum numbers of greetings to return
```

### Step 2

As per specification, the only currently possible response for `/greetings` POST 
endpoint is 200/success, add another possible response of 500/server-error along 
with a new Error schema consisting of the following fields:

  - `code`: an integer with two possible values: `1000`, `2000`
  - `message`: a string with two possible values: `'server is too busy'`, `'greeting already exists'`

#### Solution

Understand describing responses from here:
https://swagger.io/docs/specification/describing-responses/

Understand `enums` from here:
https://swagger.io/docs/specification/data-models/enums/

Add the `500` response:

```yaml
      responses:
        200:
          description: "Successful response"
          schema:
            $ref: '#/definitions/GreetingWithId'
        500:
          description: "Server Error"
          schema:
            $ref: '#/definitions/ServerError'
```

Add the definition we referenced above:

```yaml
definitions:
  ServerError:
    type: "object"
    properties:
      code:
        type: integer
        enum: 
        - 1000
        - 2000
      message:
        type: string
        enum: 
        - 'server is too busy'
        - 'greeting already exists'
```
