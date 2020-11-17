# Typescript GraphQL & TypeORM mas Postgresql pg

Esta aplicacion de ejemplo se basa en contenedores 
1 node con graphql puerto 3000
2 postgrest puerto 5432
3 pg admin 8889

Para crear los contenedores ingresar el comando 
- docker-compose up  o  docker-compose up --build

### crear la base de datos

- ir al url http://localhost:8889
- ingresar usuario graphpl
- ingresar password a1128f69-e6f7-4e93-a2df-3d4db6030abc

- Agregar un nuevo servidor
- nombre servidor test
- cambiar a pestaña de conexion 
- en nombre y direccion de servidor ingresar el ipaddressgateway del contendor de pg
- cambiar usuario y password por los definidos anteriormente
- puerto de la base 5432
- nombre de la base postgres


### uso

- ingresar al url http://localhost:3000/graphql

-  crear un nuevo producto
mutation {
  createProduct(variables:{
    name: "producto",
    quantity:10
    
  }){
    id,
    name,
    quantity,
    createdAt
  }
}

- crear un query 
{
  products{
    name,
    id
  }
}

- actualizar producto
mutation {
  updateProduct(id:1, fields:{
    name:"nuevo producto"
  })
}

- eliminar producto
mutation {
  deleteProduct(id:1)
}


