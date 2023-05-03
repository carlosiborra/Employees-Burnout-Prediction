NOTAS:

- Knn no funciona a secas

TODO:
✔️ - Cambiar la forma de imprimir los resultados, no cada uno en una tabla sino por grupo
✔️ - Explicar que metodo de boosting libreria externa usar

- Obtener los atributos eliminados seleccion
✔️ - se puede aplicar DRY in the triple pipeline
- Explicar porq sale el mismo resulatdo -> es porq los atb estan muy poco correlacionados, son importantes y solo se eleiminan los redundantes que ya estaban bajando la dimensionalidad
✔️ - Hacer comeo en la práctica anterior de explicar los atb
- Analizar el resultado de las confusion matrix -> importante cada elemento del array
✔️ - La razón por la que hemos seleccionado catboost
✔️ - Hacer tabla de parametros para catboost
- Meter las columnas del pipeline y procesos en todos -> hacerlo funciones
- Cambiar nombre de preprocessing pypeline
- Comentar que solo se modifican dos param de catboost porq ñaadir mas dispara el entrenamiento hasta mas de 1 hora y que los que faltan por modificar ya son muy buenos d epor si
- Comentar el balanced accuracy
- TODO CAMBIAR AL 2 el l2_leaf_reg
- COnclusion
- Se ha de borrar las columnas del train set? y del test?!!?!?!?!?! cuando se hace seleccion y luego se hace un fit

Preguntar:

- KNN no funciona para selección

-  CUANDO SE HACE UN PIPELINE DE TRANSFORMERS CON PREPROCESSORS DND SE HAN ELIMINADO COLUMNAS, LUEGO EN model_xgb.fit(X_train, y_train)
 TENEMOS QUE METER LAS COLUMNAS  ELIMINADAS?

- comentar que mas de dos parametros y cambiando los defaults el tiempo se dispara exponencialmente
- TARDA MUCHO!!
- no funciona el mutual info clasif para la variable ordinal
