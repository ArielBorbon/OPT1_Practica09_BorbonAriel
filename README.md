## Practica 8 de Temas Emergentes
Ariel Eduardo Borbon Izaguirre 252116


¿por qué el paquete del adaptador se llama adapter-mariadb si usamos MySQL?
porque mariadb es un fork de MySQL, entonces son relativamente "Gemelos" por lo que el controlador de Node es compatible con MySQL


¿editar schema.prisma cambió algo en la base de datos antes de migrar?
No, cuando cambias el schema.prisma solo se cambia de manera local, cuando se hace el migrate ahi si ya se reflejan en la BD real


¿la carpeta de migraciones es una foto del esquema o un historial?
es el historial, cada migracion hace un .sql con los cambios que se hicieron de version en version, para tener un registro a la mano de todos los cambios que se han hecho


¿por qué Horario.clase sí crea columna y Clase.horarios no?
porque horario.clase es el lado de la relacion que tiene la llave foranea (que seria la columna donde se guarda el id foranea) y clase.horarios es un campo oculto que usa prisma para poder acceder a los horarios desde codigo, pero sin existir como columna en la BD 


¿de dónde sale la relación de muchos a muchos entre Miembro y Horario, si nunca se declaró?
de la tabla de inscripcion, como se tiene de uno a muchos desde horario a inscripcion, y una a muchos de miembro a inscripcion, se "Asume" como muchos a muchos una relacion entre Horario y miembro
