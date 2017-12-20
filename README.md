Dokumentáció

Családi Pénztárca

Rövid Ismertető:
A Family Bridge egy olyan alkalmazás, ami abban segít a családoknak, h a szülők  nyomon tudják követetni a költéseiket  illetve gyerekeik költését, és 
Az admin jogú felhasználó a saját és user jogu felhasználók költéseit is látja, a user csak a sajátját.

A fejlesztői környezet és eszközök bemutatása:

	A project a NetBeans nevű fejlesztői környezetben készült a Maven Project, mely egy olyan fejlesztői eszköz, amivel könyen lehet	elhasználni más modulokat/plug-in-eket és leszedi ehez a szükséges dependencyket(függőségeket). Valamint a Spring Boot 			felhasználásával, mely egy olyan eszköz melyel könnyen és gyorsan lehet prototipusokat létrehozni. Továbbá felhasználtuk a h2 		adatbázis motort is a projectben, mely Java SQL adatbázist vezényel, valamint a Lombok nevű plug-int aminek köszönhetőleg nem 		kell gettereket írni, valamint összehasonlító(equals) metódusokat.

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


Nem funkcionális követelmények:

	gyorsaság
	biztonság
	megbízhatóság
 	könnyű kezelés
