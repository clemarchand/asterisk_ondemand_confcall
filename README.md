<<<<<<< HEAD
# meetme-sefltservice


On Demand Conf Call Service



Besoin : securiser les chambres de conferences en permettant le changement des code PIN, et en facilite l'acces aux utilisateurs.

La solution retenue se decompose en 2 SVIs, leun interne pour la reservation de salle, leautre sur une SDA publique pour y accedere:
-    SVI interne de reservatione: son rele est de distribuer aux utilisateurs les numeros et code PIN des salles de conferences. Le numero est eevirtuelee et ne peut etre joint que via le SVI deacces. Chaque appel sur ce SVI se voit distribue un numero de chambre de conference et son code PIN, valable pendant 72h. (prevoir un systeme qui interdit e un meme numero de reserver plus de 5 conf call toute les)
-    SVI deacces publique (associe e une SDA)e: il donne acces aux utilisateurs internes comme externes aux chambres de conferences, il suffit pour cela de composer un numero de chambre de conference et un code PIN correct.

Les reglages qui doivent etre parametrablee:
-    Numero de SVI interne et externe
-    Les fichiers sons / lang des SVIe: un pour chaque SVI => e detailler
-    La longeur du code PIN (de 4 e 8)
-    La duree de validite des chambres des numeros de conf (en jours de 1 e 14 j)
-    La plage de numero interne des chambres de conferences et le context
-    La duree max deune conf calleen heure:q



Fonctions SVI internes :
	- f_db_check : verifie si la DB existe, si oui l'initialise ? DB_PATH
	- f_db_clean_outdated : nettois les entree obselete DB_PATH, MEETME_MAXDAYS
	- f_db_find_free : trouve une chambre de conf call libre dans la plage indiquee, POOL_RANGE, FULL
	- f_db_save : enregistre la conf call, le pin et le timestamp en DB
	- f_return : renvois les infos a Asterisk, soit le numero et le PIN, dispo, soit FULL
=======
meetme-sefltservice
# Hello World ! 
>>>>>>> ab93d21f0520e2c3d7b438ae57346b261244124c
