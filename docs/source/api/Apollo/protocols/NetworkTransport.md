**PROTOCOL**

# `NetworkTransport`

```swift
public protocol NetworkTransport: class
```

> A network transport is responsible for sending GraphQL operations to a server.

## Properties
### `clientName`

```swift
var clientName: String
```

> The name of the client to send as the `"apollographql-client-name"` header.

### `clientVersion`

```swift
var clientVersion: String
```

> The version of the client to send as the `"apollographql-client-version"` header

## Methods
### `send(operation:completionHandler:)`

```swift
func send<Operation>(operation: Operation, completionHandler: @escaping (_ result: Result<GraphQLResponse<Operation>, Error>) -> Void) -> Cancellable
```

> Send a GraphQL operation to a server and return a response.
>
> - Parameters:
>   - operation: The operation to send.
>   - completionHandler: A closure to call when a request completes. On `success` will contain the response received from the server. On `failure` will contain the error which occurred.
> - Returns: An object that can be used to cancel an in progress request.

#### Parameters

| Name | Description |
| ---- | ----------- |
| operation | The operation to send. |
| completionHandler | A closure to call when a request completes. On `success` will contain the response received from the server. On `failure` will contain the error which occurred. |