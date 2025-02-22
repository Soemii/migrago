***
# ARCHIVED
**Personal project that was used for a custom code structure that is no longer needed, so it is now archived. I now use [golang-migrate](https://github.com/golang-migrate/migrate).**
***
# migrago
Database migration tool for go projects

> Currently only supports postgres databases

## WARNING
> This is a work in progress and should not be used in production

## features
- [x] Database migration
- [x] Rollback migration
- [x] Configurable migration directory
- [x] Support postgres
- [ ] Support mysql
- [ ] Support sqlite


## installation
use the following command to install the package

```bash
go get github.com/Soemii/migrago@v1.0.0
```

## usage
```go
db, err := sql.Open("postgres", dsn)
if err != nil {
	return nil, err
}
fs := os.DirFS("migration")
service := migrago.NewMigrationService("config.json", "scripts", fs, db)
err = service.ExecuteMigration(context.Background())
```
## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](https://raw.githubusercontent.com/Soemii/migrago/refs/heads/main/LICENSE)
