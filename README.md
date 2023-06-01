# Interconnexion Reconnect Pro - INS Sésame Vitale

## 0. Principe global

* Se connecter via des calls à une api SOAP : avec [Cette librairie](https://github.com/phpro/soap-client) ou avec l’extension [php-soap](https://www.php.net/manual/en/book.soap.php)
* Utiliser le workflow Vérification unitaire seule (workflow A)
* Le tout avec et sans carte vitale

## 1. Récupération de l’INS d’un patient:

**WSDL:** DESIR_ICIR_EXP_1.5.0.wsdl (du 06/11/2020)

11.  **Avec Carte vitale :**
* **Action:** rechercherInsAvecCarteVitale (v1.0.0)
* **Messages:** rechercherInsAvecCarteVitale, rechercherInsAvecCarteVitaleResponse
* **Payload:**  CF fichier [get_ins_vitale.xml](./get_ins_vitale.xml)

12. **Sans Carte vitale :**
* **Action:** rechercherInsAvecTraitsIdentite (v1.0.0)
* **Messages:** rechercherInsAvecTraitsIdentite, rechercherInsAvecTraitsIdentiteResponse
* **Payload:**  CF fichier [get_ins_identity.xml](./get_ins_identity.xml)

## 2. Vérification de l’INS d’un patient:

21. **Vérification unitaire :**
* **Action:** rechercherInsAvecTraitsIdentite (v1.0.0)
* **Messages:** rechercherInsAvecTraitsIdentite, rechercherInsAvecTraitsIdentiteResponse
* **Payload:**  CF fichier [check_ins.xml](./check_ins.xml)

## Prochaines étapes :

Clarifier le méchanisme d'authentification:

* Certificat logiciel
* CPx

Dans les 2 cas, comment obtenir la clé d'authenth, et comment l'envoyer à l'API
