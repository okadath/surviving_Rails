install RVM:
```

curl -L https://get.rvm.io | bash -s stable --ruby

echo "[[ -r $rvm_path/scripts/completion ]] && source $rvm_path/scripts/completion" >> ~/.bashrc

source ~/.bashrc
```

listar versiones(no ambientes):
```
rvm list
```
usar
```
rvm install 1.8.7
rvm use 1.8.7
  remove                  # remove ruby and downloaded sources
  requirements            # installs dependencies for building ruby

```
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
y ya habiendolo seleccionado lo usamos como normalmente se hace:
```
gem install redcarpet
```
para borrarlo:
```
rvm gemset delete env_test
```



### Ruby+Postgres
hay problemas de dependencias con los rivers para postgres(aun usando la version actual de ruby 2.6)
loq ue se debe hacer es bajar el driver de postgres:

```
sudo aptitude install libpq-dev
```
y elegir bajar el nivel de la dependencia


### Postgres

algunas gemas necesitan una db specifica:
```
rails new testapp -d postgresql
```

los instalamos con apt y creamos su usuario
antes debimos haber creado el usuario postgres o debe ser posible logearse con el con 
`sudo -u postgres -i`

tambien podemos logearnos con 
`su - postgres` y usando postgres como pass

creamos el usuario:

```
sudo -u postgres createuser okadath
```

y creamos la abse de datos perteneciente a ese usuario:
```
createdb -O okadath testapp_development
```

y migramos:
```
rails db:migrate
```
