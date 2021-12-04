# Lab 6 Assignment
Specification and documentation of a systems Application Programming Interface (API) is an essential part of any architecture documentation and serves multiple stakeholders. In this lab, you will work with OpenAPI specification language to study and experiment with the specification of a RESTful API of a simple PetStore service, use Swagger UI to generate an interactive web-based documentation, and Swagger Codegen to generate a fully functional mock server.

## Links

- [Deliverables](./DELIVERABLES.md)
- [NodeJS Server: Pet Swagger](./nodejs-server)

## Steps

  - Step 1: familiarize yourself with the Swagger toolset: https://swagger.io/

  - Step 2: use Swagger Editor and learn key features of the specification language: https://editor.swagger.io/

  - Step 3: generate and download a mock server of your choice using the “Generate Server” tab, Swagger can generate various types of servers including Java-based, Python-flask, nodejs-server and many more.

The downloaded mock server contains a README file, follow the instructions listed in the README file to run a local instance of the mock server, the server binds to a local port and can be used to invoke all functions specified in your API specification.

## Deliverables

  - Screenshots showing a successful invocation of `/store/inventory` API endpoint.

  - Screenshot showing a successful invocation of `/pet/{petId}` endpoint, you can obtain a valid PET ID using the /pet/findByStatus endpoint.

  - For the endpoint `/store/order` (POST), show an example json request payload.

  - Screenshot showing that the mock server runs successfully on your local machine.

### Optional

Study and use Swagger Editor to test a YAML specification of a greeter API system ( [CLICK TO DOWNLOAD](https://lewisuniversity.blackboard.com/bbcswebdav/pid-4800775-dt-content-rid-44449139_1/xid-44449139_1) ). The specification supports posting of a greeting json payload and retrieving of all greetings. Modify the specifications as follows:

  - Add `limit` query parameter to the `/greetings` GET endpoint, `limit` is an integer value and represents the maximum number of greetings that can be returned by the endpoint.

  - As per specification, the only currently possible response for `/greetings` POST endpoint is 200/success, add another possible response of 500/server-error along with a new Error schema consisting of the following fields:

    - `code`: an integer with two possible values: 1000, 2000
    - `message`: a string with two possible values: `“server is too busy”`, `“greeting already exists”`
 
Submit your modified YAML specification and a screenshot showing the new API documentation in Swagger UI reflecting above modifications.
