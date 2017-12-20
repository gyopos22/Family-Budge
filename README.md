Dokumentáció

Családi Pénztárca

Rövid Ismertető:
A Family Bridge egy olyan alkalmazás, ami abban segít a családoknak, h a szülők  nyomon tudják követetni a költéseiket  illetve gyerekeik költését, és 
Az admin jogú felhasználó a saját és user jogu felhasználók költéseit is látja, a user csak a sajátját.

A fejlesztői környezet és eszközök bemutatása:

A project a NetBeans nevű fejlesztői környezetben készült a Maven Project, mely egy olyan fejlesztői eszköz, amivel könyen lehetelhasználni más modulokat/plug-in-eket és leszedi ehez a szükséges dependencyket(függőségeket). Valamint a Spring Boot 		felhasználásával, mely egy olyan eszköz melyel könnyen és gyorsan lehet prototipusokat létrehozni. Továbbá felhasználtuk a h2 	adatbázis motort is a projectben, mely Java SQL adatbázist vezényel, valamint a Lombok nevű plug-int aminek köszönhetőleg nem 	kell gettereket írni, valamint összehasonlító(equals) metódusokat.

Funkciók:

	Regisztráció:  email cím és jelszó megadásával történik.
	
	Bejelentkezés:  email cím és jelszó megadásával történik.
	
	Kijelentkezés: a felhasználót a rendszer nem engedi a loginon és a regisztráción kívül
   			 beengedni
 	Tranzakciók megtekintése:A user és az admin is megtudja tekinteni korábbi költéseit és részleteit.
	
	Tranzakció hozzáadása: A user és az admin felhasználó is hozzá tud adni vagy venni pénzt a számlájához.
	
 	Kérelem: a user felhasználó pénzt tud kérvényezni az admin jogú tagról.
	
 	Kérelmek: csak az admin jogú tag látja, elfogadni vagy elutasítani tudja a kérelmeket.
	
  
Felhasználók

 	Admin: admin jogú felhasználó a saját és user jogu felhasználók költéseit is látja. hozzá tud adni költést és jövedelmet,eltud 			fogadni kérvényeket
	
	User: csak a saját költéseit látja. Hozzá tud adni költést, és tud kérvényezni az admin jogú tagtól pénzt.
	
	Guest: Csak a login és a register oldal érhető el neki

A forrás fájlok a familybudge nevű főkönyvtárban található, mely több alkönyvtárra ágazik szét:	
	annotation	
	config	controller
	entity
	repository
	service

Nem funkcionális követelmények:


	gyorsaság
	biztonság
	megbízhatóság
 	könnyű kezelés

	

Végpont-tervek és leírások:

A controllerek valósítják meg a végpontokat. 
A UserController a "/api/user" végpontra dolgozik. A metódusai meg ezen belül osztódnak el 3 végső végpontra.
A register metódus a "/register" végponton fogadja a bejövő adatokat.
A login metódus a "/login" végponton fogadja a bejövő adatokat.
A logout metódus a "/logout" végponton fogadja a bejövő adatokat.
A TransactionController a "/api/transaction" végpontra dolgozik.  Itt igazából mindig az lesz a végpont ami az adott transaction id-je(azonosítója). Ezek a metódusok dolgoznak a végponra: create, update, read, delete.
A RequestController a "/api/request" végpontra dolgozik. Itt igazából mindig az lesz a végpont ami az adott request id-je(azonosítója). Ezek a metódusok dolgoznak a végponra: create, read, update, delete.
1db végpont működésének leírása:

Vegyük pl a UserController osztályt. A UserController osztály a "/api/user" végpontra dolgzik. Ezen belül vegyük pl a register metódusát ami a "/register" dolgozik az elözőn belül, tehát a "/api/user/register" végpontra fog érkezni a kérés. Ezt a Controller elkapja, majd mivel csak a register metódus van ezen a végponton a register metódus tovább küldi a UserService register nevű metódusának, mely aztán a létrehozott usernek beállít még egy rolet(User vagy Admin) majd meghívja a UserRepository save metódusát, mely elmenti az adatbázisban a beadott adatokat. És itt véget ér a folyamat.
