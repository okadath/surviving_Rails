# README

listar el actual:
```
rvm use
```
para crear un ambiente(gemset):
```
rvm gemset create project1
```
para usarlo:
```
rvm gemset use project1
rvm @project1
rvm 1.9.3@project1
```
para listar los ambientes actuales:
```
rvm gemset list
```
usar el gemset correcto:
```
rvm gemset use env_rails
```

### Install

creamos un proyecto:
```
rails new testapp -d postgresql
```

instalamos `gem spina` en bash y en el gemfile
luego lo instalamos desde rails 
```
rails g spina:install
```
y migramos `rails db:migrate`

para ejecutar desde el admin
