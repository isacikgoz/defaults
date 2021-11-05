# defaults

Defaults lets you define default values for structs. Also, you can add pre-defined validation rules to validate struct fields.

```Go
type Instance struct {
	URL      string `default:"https://isacikgoz.me" validate:"url"`
	Login    string `validate:"email"`
	Password string `validate:"notempty"`
}
```

## Examples

To set default values you can simply use as following

```Go
var i Instance
err := defaults.Set(&i)
if err != nil {
	panic(err)
}
```

Or you can validate if the struct fields are valid

```Go
i := Instance{
	URL:      "https://isacikgoz.me",
	Login:    "isacikgoz@me.com",
	Password: "my-super-secret-password",
}

err := defaults.Validate(&i)
if err != nil {
	panic(err)
}
```
