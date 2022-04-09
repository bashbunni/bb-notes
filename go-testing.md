# Testing in Go 

## Gathering Intel for Tests 

`go test -coverprofile cover.out && go tool cover -html=cover.out`
^^^ this doesn't work -> doesn't pick up my tests

``` go
func ILikePotatoes() {
  fmt.Println("I really do like potatoes")
}
```

## Mocks and Stubs
### Mocks
- avoid using mocks when possible, they should only be used sparingly
when to use mocks: "how does this perform with many many things" -> or things that are out of your control

## PJs Testing (Project Journal CLI tool)
### Small Projects
- find a way to test the code you wrote
- Gorm support in-memory DBs for Testing
  - if it were more complex, you could have a staged environment to test against


#### Next Steps
1. create a DB the same way you would when you run (i.e. include schema, etc) -> return that DB
2. add projects to DB
3. check that the projects return the correct values
  - GetProjects -> check the # of projects, the name
  - Write SQL to get the results back and check against that -> use this to check DB state etc (could be a duplicate of what your GetProjects does)

- each test case can be completely isolated i.e. create a new DB with each test case
- de-coupling -> more pure functions -> a function that takes a list of tasks (doesn't talk to DB), then calculates x and returns that. 
