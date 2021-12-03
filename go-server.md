## HTTP Server Setup

`func ListenAndServe(addr string, handler Handler) error`

- starts a web server listening on a port and creating a goroutine for every request and running it against a Handler

```
type Handler interface {
	ServeHTTP(ResponseWriter, *Request)
}
```

ResponseWriter is our response, \*Request is the request sent to the server

**By doing the bare minimum to make the tests pass it can highlight gaps in your tests.**

## Working with MySQL

- the `Exec` command should be used for INSERT, UPDATE, DELETE or any other statement that doesn't return rows.
- Using the `Query` command can cause you to run out of resources quickly (See "Modifying Database Info")
  `db.Exec("DELETE FROM users")`

## Resources

[Golang MySQL Tutorial](https://tutorialedge.net/golang/golang-mysql-tutorial/)
[Modifying Database Info](http://go-database-sql.org/modifying.html)
