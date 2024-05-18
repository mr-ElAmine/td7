# 1. Classe
En Java, une classe est un peu comme un plan pour créer quelque chose. Imagine que tu veux construire une maison. Avant de commencer à construire, tu fais un plan qui décrit à quoi ressemblera la maison, combien de chambres elle aura, où seront les fenêtres, etc. Eh bien, une classe est comme ce plan pour créer des objets.

Par exemple, tu peux avoir une classe `Voiture`. Cette classe décrit ce qu'est une voiture : quelles sont ses caractéristiques (comme la marque, le modèle, l'année), et ce qu'elle peut faire (comme démarrer, accélérer, s'arrêter).

Ensuite, une fois que tu as ce plan, tu peux créer des voitures spécifiques à partir de ce plan. Ces voitures spécifiques sont appelées des "objets". Chaque objet a ses propres valeurs pour les caractéristiques, mais suit toujours le plan (la classe).

Voici un exemple simple de classe `Voiture` en Java :

```java
public class Voiture {
    // Caractéristiques de la voiture
    String marque;
    String modele;
    int annee;

    // Actions que la voiture peut faire
    public void demarrer() {
        System.out.println("La voiture démarre !");
    }

    public void accelerer() {
        System.out.println("La voiture accélère !");
    }

    public void arreter() {
        System.out.println("La voiture s'arrête !");
    }
}
```

Dans cet exemple :

- `Voiture` est le nom de la classe.
- `marque`, `modele` et `annee` sont les caractéristiques de la classe.
- `demarrer()`, `accelerer()` et `arreter()` sont les actions que la voiture peut faire.

Ensuite, tu peux créer des voitures spécifiques à partir de cette classe comme ceci :

```java
public class Main {
    public static void main(String[] args) {
        // Créer une voiture spécifique
        Voiture maVoiture = new Voiture();
        
        // Définir ses caractéristiques
        maVoiture.marque = "Toyota";
        maVoiture.modele = "Corolla";
        maVoiture.annee = 2020;

        // Utiliser les actions de la voiture
        maVoiture.demarrer();
        maVoiture.accelerer();
        maVoiture.arreter();
    }
}
```

Cela donnera une sortie comme :

```
La voiture démarre !
La voiture accélère !
La voiture s'arrête !
```
# 2. Constructeur
Un constructeur en Java est une méthode spéciale qui est appelée automatiquement lorsque tu crées une instance (un objet) d'une classe. Son rôle principal est d'initialiser les variables de l'objet et de configurer tout ce qui est nécessaire pour que l'objet soit utilisable.

Voici quelques points importants à retenir sur les constructeurs en Java :

1. **Nom de la méthode**: Le nom du constructeur doit être le même que le nom de la classe.

2. **Pas de type de retour explicite**: Les constructeurs n'ont pas de type de retour (pas même `void`).

3. **Initialisation des variables**: Tu peux utiliser un constructeur pour initialiser les variables de l'objet.

4. **Plusieurs constructeurs**: Tu peux avoir plusieurs constructeurs dans une classe. C'est ce qu'on appelle la surcharge de constructeurs.

Voici un exemple pour illustrer ces points :

```java
public class Voiture {
    // Caractéristiques de la voiture
    String marque;
    String modele;
    int annee;
    
    // Constructeur avec des paramètres
    public Voiture(String marque, String modele, int annee) {
        this.marque = marque;
        this.modele = modele;
        this.annee = annee;
    }
    
    // Méthode pour afficher les informations de la voiture
    public void afficherInfos() {
        System.out.println("Marque : " + marque);
        System.out.println("Modèle : " + modele);
        System.out.println("Année : " + annee);
    }
}
```

Dans cet exemple :

- Il y a un constructeurs avec des paramètres.
- Le constructeur avec des paramètres permet d'initialiser les variables avec des valeurs fournies lors de la création de l'objet.
- `this` est utilisé pour faire référence aux variables de l'instance de la classe.

Voici comment tu peux utiliser ces constructeurs :

```java
public class Main {
    public static void main(String[] args) {
         // Créer une voiture
        Voiture voiture2 = new Voiture("Toyota", "Corolla", 2020);
        System.out.println("\nVoiture 2 :");
        voiture2.afficherInfos();
    }
}
```

La sortie sera :

```
Voiture 2 :
Marque : Toyota
Modèle : Corolla
Année : 2020
```

Comme tu peux le voir, le constructeur est utilisés pour initialiser les objets de manière appropriée, ce qui rend l'utilisation des objets plus sûre et plus pratique. Plus sûre comment ça ?

# 3. Getters et Setters
Avant de commencer, on doit voir la déclaration de variable en JAVA. Elle peut se représenter comme ceci:
```
[typeAccess] typeDeVariable nomDeVariable = valeur;
```

D'accord, voici votre texte mis en forme avec les niveaux d'accès et les types de variables :

En Java, les variables peuvent avoir différents niveaux d'accès, déterminant qui peut accéder à la variable et comment elle peut être utilisée. Les quatre niveaux d'accès principaux sont :

1. **public** : La variable est accessible par n'importe quelle classe.
2. **protected** : La variable est accessible par les classes du même paquetage et par les sous-classes (classes qui héritent de cette classe).
3. **default** (ou package-private) : La variable est accessible uniquement par les classes du même paquetage.
4. **private** : La variable est accessible uniquement à l'intérieur de la classe où elle est déclarée.

En Java, les variables peuvent avoir différents types, permettant de stocker différentes formes de données. Voici les types de variables les plus couramment utilisés :

1. **int** : pour stocker des nombres entiers.
2. **double** : pour stocker des nombres décimaux à virgule flottante avec une grande précision.
3. **float** : pour stocker des nombres décimaux à virgule flottante avec une précision moindre.
4. **boolean** : pour stocker des valeurs booléennes (true ou false).
5. **char** : pour stocker un seul caractère Unicode.
6. **String** : pour stocker une séquence de caractères.

En ce qui concerne les noms de variables, voici quelques exemples de bonnes pratiques :

- **CamelCase** : Commencer par une lettre minuscule, puis chaque mot commençant par une majuscule (sauf pour la première lettre de la première variable), par exemple : `age`, `nomComplet`, `estMajeur`.
- **Clarté** : Choisissez des noms de variables qui décrivent bien leur but ou leur contenu. Par exemple, `age` pour stocker l'âge d'une personne, `prixUnitaire` pour le prix unitaire d'un produit.
- **Concision** : Évitez les noms de variables trop longs, mais suffisamment descriptifs. Un nom de variable doit être suffisamment clair pour que quelqu'un d'autre puisse comprendre sa signification sans avoir besoin de commentaires supplémentaires.
- **Évitez les abréviations non claires** : Utilisez des abréviations uniquement si elles sont largement comprises et évidentes. Par exemple, `num` pour un numéro peut être acceptable, mais des abréviations plus obscures peuvent rendre le code difficile à comprendre.

Voici quelques exemples :
```java
private int age = 25; // Déclaration d'un entier avec accès privé et valeur initiale 25
public String nom = "Jean"; // Déclaration d'une chaîne de caractères avec accès public et valeur initiale "Jean"
protected double poids = 65.5; // Déclaration d'un nombre à virgule flottante avec accès protégé et valeur initiale 65.5
boolean estMajeur; // Déclaration d'un booléen avec accès par défaut et aucune valeur initiale
```

Alors cette combinaison de niveaux d'accès et de types de variables permet de contrôler l'accès aux données et de stocker différents types de valeurs dans vos programmes Java.

Parfait, donc continuons avec les **getters** et **setters** ! Les getters et setters sont des méthodes très utiles pour accéder et modifier les variables d'instance d'une classe. Ils permettent de contrôler l'accès aux données et de maintenir l'encapsulation, ce qui signifie que les détails internes de la classe restent cachés à l'extérieur de la classe.

Reprenons notre exemple de classe Voiture et ajoutons des getters et des setters pour ses caractéristiques :
```java
public class Voiture {
    // Caractéristiques de la voiture
    private String marque;
    private String modele;
    private int annee;
    
	 // Constructeur avec des paramètres
    public Voiture(String marque, String modele, int annee) {
        this.marque = marque;
        this.modele = modele;
        this.annee = annee;
    }
	
    // Getter pour la marque
    public String getMarque() {
        return marque;
    }
    
    // Setter pour la marque
    public void setMarque(String marque) {
        this.marque = marque;
    }
    
    // Getter pour le modèle
    public String getModele() {
        return modele;
    }
    
    // Setter pour le modèle
    public void setModele(String modele) {
        this.modele = modele;
    }
    
    // Getter pour l'année
    public int getAnnee() {
        return annee;
    }
    
    // Setter pour l'année
    public void setAnnee(int annee) {
        this.annee = annee;
    }
    
    // Méthode pour afficher les informations de la voiture
    public void afficherInfos() {
        System.out.println("Marque : " + marque);
        System.out.println("Modèle : " + modele);
        System.out.println("Année : " + annee);
    }
}
```
Décomposons notre classe `Voiture`.

```java
public class Voiture {
    // Caractéristiques de la voiture
    private String marque;
    private String modele;
    private int annee;
```

- `private`: C'est un modificateur d'accès qui indique que ces variables ne sont accessibles que depuis l'intérieur de la classe `Voiture`. Elles ne peuvent pas être directement modifiées ou consultées à partir de l'extérieur de la classe. Cela permet de respecter l'encapsulation, un principe important en programmation orientée objet où les détails internes de la classe sont cachés et protégés de toute modification non autorisée.

- `String marque;`, `String modele;`, `int annee;`: Ce sont les variables d'instance de la classe `Voiture`, ce qui signifie qu'elles appartiennent à chaque objet `Voiture` individuel que nous créons. Elles stockent les données spécifiques à chaque voiture. 

Déclarer ces variables en tant que `private` assure que seule la classe `Voiture` elle-même peut y accéder directement. Cela signifie que pour lire ou modifier ces variables depuis l'extérieur de la classe, nous devons utiliser des méthodes spéciales appelées "getters" et "setters".

Maintenant, regardons les méthodes getters et setters :

```java
    // Getter pour la marque
    public String getMarque() {
        return marque;
    }
    
    // Setter pour la marque
    public void setMarque(String marque) {
        this.marque = marque;
    }
    
    // Getter pour le modèle
    public String getModele() {
        return modele;
    }
    
    // Setter pour le modèle
    public void setModele(String modele) {
        this.modele = modele;
    }
    
    // Getter pour l'année
    public int getAnnee() {
        return annee;
    }
    
    // Setter pour l'année
    public void setAnnee(int annee) {
        this.annee = annee;
    }
```

- **Les getters**: Ce sont des méthodes publiques qui permettent de récupérer la valeur des variables privées (`marque`, `modele` et `annee`). Ils sont utilisés pour accéder à ces valeurs depuis l'extérieur de la classe. Par exemple, `getMarque()` renvoie la valeur de la variable `marque`.

- **Les setters**: Ce sont également des méthodes publiques qui permettent de modifier les valeurs des variables privées. Ils prennent en général un paramètre qui représente la nouvelle valeur de la variable. Par exemple, `setMarque(String marque)` permet de modifier la variable `marque` avec une nouvelle valeur passée en paramètre.

En utilisant ces getters et setters, nous assurons un accès contrôlé aux variables d'instance de la classe `Voiture`, ce qui garantit un bon niveau d'encapsulation et de sécurité dans notre programme.

# 4. Méthode
Le principe de méthode nous permet de regrouper des instructions liées ensemble, facilitant ainsi la réutilisation et la maintenance du code. En encapsulant la logique dans des méthodes, nous pouvons appeler ces méthodes chaque fois que nous avons besoin de réaliser une tâche spécifique, sans avoir à répéter le code. C'est un concept fondamental de la programmation orientée objet et de la modularité du code.

Dans la classe `Voiture`, `afficherInfos` est une méthode. Elle est définie comme suit :

```java
// Méthode pour afficher les informations de la voiture
public void afficherInfos() {
    System.out.println("Marque : " + marque);
    System.out.println("Modèle : " + modele);
    System.out.println("Année : " + annee);
}
```
Lorsque cette méthode est appelée, le programme exécute les instructions à l'intérieur du bloc de code. Par exemple, si nous avons une instance de la classe `Voiture` nommée `maVoiture`, nous pouvons appeler cette méthode sur cette instance :

```java
Voiture maVoiture = new Voiture("Toyota", "Corolla", 2020);
maVoiture.afficherInfos();
```

Ce qui affichera :

```
Marque : Toyota
Modèle : Corolla
Année : 2020
```
### Pour commencer il faut créer un nouveau projet

# 1. Compte Bancaire :
Puis faut créer une classe et l'appeler `CompteBancaire` sont code est:
```Java
class CompteBancaire  {
	protected String numero;
	protected Client titulaire;
	protected float solde;
	protected String devise;

	public CompteBancaire (
			String numero, 
			Client titulaire, 
			float solde, 
			String devise
			) {
		this.numero = numero;
		this.titulaire = titulaire;
		this.solde = solde;
		this.devise = devise;
	}


	public String getNumero() {
		return numero;
	}

	public void setNumero(String numero) {
		this.numero = numero;
	}

	public Client getTitulaire() {
		return titulaire;
	}

	public void setTitulaire(Client titulaire) {
		this.titulaire = titulaire;
	}

	public float getSolde() {
		return solde;
	}

	public void setSolde(float solde) {
		this.solde = solde;
	}

	public String getDevise() {
		return devise;
	}

	public void setDevise(String devise) {
		this.devise = devise;
	}
	
    public void debiter(float montant) {
        if (montant > 0 && montant <= solde) {
            solde -= montant;
            System.out.println("Débit de " + montant + " " + devise + " effectué.");
        } else {
            System.out.println("Montant invalide ou solde insuffisant.");
        }
    }

    public void crediter(float montant) {
        if (montant > 0) {
            solde += montant;
            System.out.println("Crédit de " + montant + " " + devise + " effectué.");
        } else {
            System.out.println("Montant invalide.");
        }
    }
    
    public String decrire() {
        return "n°: " + numero + " - solde : " + solde + " " + devise;
    }
}
```
### Explication :
### Attributs de la classe `CompteBancaire` :
- `numero`: Cet attribut représente le numéro du compte bancaire.
- `titulaire`: Cet attribut est de type `Client` et représente le titulaire du compte.
- `solde`: Cet attribut représente le solde du compte.
- `devise`: Cet attribut représente la devise du compte.

### Constructeur `CompteBancaire` :
- Il initialise un objet `CompteBancaire` avec les valeurs passées en paramètres.

### Getters et Setters :
- Les méthodes `getNumero()`, `getTitulaire()`, `getSolde()`, `getDevise()` permettent d'obtenir les valeurs des attributs.
- Les méthodes `setNumero()`, `setTitulaire()`, `setSolde()`, `setDevise()` permettent de modifier les valeurs des attributs.

### Méthodes `debiter()` et `crediter()` :
- `debiter(float montant)`: Cette méthode permet de débiter un montant donné du compte. Si le montant est valide et que le solde est suffisant, le montant est débité du solde du compte.
- `crediter(float montant)`: Cette méthode permet de créditer un montant donné sur le compte. Si le montant est valide, il est ajouté au solde du compte.
- Ces méthodes affichent un message selon que l'opération a réussi ou non.

### Méthode `decrire()` :
- Cette méthode retourne une chaîne de caractères décrivant le compte. Elle affiche le numéro du compte et son solde avec la devise associée.

#2. Client 

Faut créer une autre classe et l'appeler `Client` sont code est:
```Java
import java.util.Date;
import java.util.ArrayList;

class Client {
	private String nom;
	private String prenom;
	private boolean genre;
	private Date dateDeNaissance;
	private String categorieSocioProfessionnelle;
	private String adresse;
	private String telephone;
	private String email;
    private ArrayList<CompteBancaire> comptes;

	public Client(
			String nom, 
			String prenom, 
			boolean genre, 
			Date dateDeNaissance, 
			String categorieSocioProfessionnelle,
			String adresse, 
			String telephone, 
			String email
			) {
		this.nom = nom;
		this.prenom = prenom;
		this.genre = genre;
		this.dateDeNaissance = dateDeNaissance;
		this.categorieSocioProfessionnelle = categorieSocioProfessionnelle;
		this.adresse = adresse;
		this.telephone = telephone;
		this.email = email;
		this.comptes = new ArrayList<CompteBancaire>();
	}

	public String getNom() {
		return nom;
	}

	public void setNom(String nom) {
		this.nom = nom;
	}

	public String getPrenom() {
		return prenom;
	}

	public void setPrenom(String prenom) {
		this.prenom = prenom;
	}

	public boolean isGenre() {
		return genre;
	}

	public void setGenre(boolean genre) {
		this.genre = genre;
	}

	public Date getDateDeNaissance() {
		return dateDeNaissance;
	}

	public void setDateDeNaissance(Date dateDeNaissance) {
		this.dateDeNaissance = dateDeNaissance;
	}

	public String getCategorieSocioProfessionnelle() {
		return categorieSocioProfessionnelle;
	}

	public void setCategorieSocioProfessionnelle(String categorieSocioProfessionnelle) {
		this.categorieSocioProfessionnelle = categorieSocioProfessionnelle;
	}

	public String getAdresse() {
		return adresse;
	}

	public void setAdresse(String adresse) {
		this.adresse = adresse;
	}

	public String getTelephone() {
		return telephone;
	}

	public ArrayList<CompteBancaire>getComptes() {
		return comptes;
	}

	public void setComptes(ArrayList<CompteBancaire>comptes) {
		this.comptes = comptes;
	}

	public void setTelephone(String telephone) {
		this.telephone = telephone;
	}

	public String getEmail() {
		return email;
	}

	public void setEmail(String email) {
		this.email = email;
	}
	
    public void info_comptes() {
        System.out.println("Liste des comptes de " + prenom + " " + nom + ":");
        for (CompteBancaire compte : comptes) {
            System.out.println(compte.decrire());
        }
    }
}
```
### Explication :
### Attributs de la classe `Client` :
- `nom`, `prenom`: Ces attributs représentent respectivement le nom et le prénom du client.
- `genre`: Cet attribut indique le genre du client. Il est de type booléen, où `true` représente un genre masculin et `false` un genre féminin.
- `dateDeNaissance`: Cet attribut de type `Date` représente la date de naissance du client.
- `categorieSocioProfessionnelle`: Cet attribut représente la catégorie socio-professionnelle du client.
- `adresse`, `telephone`, `email`: Ces attributs représentent l'adresse, le numéro de téléphone et l'email du client.
- `comptes`: C'est une liste (ArrayList) des comptes bancaires du client.

### Constructeur `Client` :
- Il initialise un objet `Client` avec les valeurs passées en paramètres.

### Getters et Setters :
- Les méthodes `getNom()`, `getPrenom()`, `isGenre()`, `getDateDeNaissance()`, `getCategorieSocioProfessionnelle()`, `getAdresse()`, `getTelephone()`, `getEmail()` permettent d'obtenir les valeurs des attributs.
- Les méthodes `setNom()`, `setPrenom()`, `setGenre()`, `setDateDeNaissance()`, `setCategorieSocioProfessionnelle()`, `setAdresse()`, `setTelephone()`, `setEmail()` permettent de modifier les valeurs des attributs.
- Les méthodes `getComptes()` et `setComptes()` permettent respectivement d'obtenir et de définir la liste des comptes bancaires du client.

### Méthode `info_comptes()` :
- Cette méthode affiche les informations de tous les comptes bancaires du client. Elle parcourt la liste `comptes` et pour chaque compte, elle appelle la méthode `decrire()` du compte bancaire pour obtenir sa description.

___
**Le principe d'héritage de classe est un concept fondamental de la programmation orientée objet (POO) qui permet à une classe d'hériter des caractéristiques (attributs et méthodes) d'une autre classe. Cela permet de créer une hiérarchie entre les classes, où les sous-classes (ou classes dérivées) héritent des caractéristiques d'une classe parente (ou classe de base), tout en pouvant ajouter leurs propres fonctionnalités spécifiques.**
___
#2. Compte Epargne 
Faut créer une autre classe et l'appeler `CompteEpargne` sont code est:
```Java
class CompteEpargne extends CompteBancaire {
	private float taux;

	public CompteEpargne(String numero, Client titulaire, float solde, String devise, float taux) {
		super(numero, titulaire, solde, devise);
		this.taux = taux;
	}

	public void ajouterInteret() {
		if (getSolde() >= 0) {
			float interet = getSolde() * (taux / 100);
			crediter(interet);
			System.out.println("Intérêts ajoutés au compte épargne " + getNumero() + ": " + interet + " " + getDevise());
		}
	}

	public String decrire() {
		return "Compte épargne n°: " + getNumero() + " - solde : " + getSolde() + " " + getDevise() + " - Taux d'intérêt : " + taux 	+ "%";
	}
	
    public void debiter(float montant) {
        if (montant > 0) {
        	float demiSolde = getSolde() / 2;
            if (montant <= demiSolde) {
                debiter(montant);
            } else {
                System.out.println("Opération impossible: vous ne pouvez pas retirer plus de la moitié du solde en une seule fois.");
            }
        } else {
            System.out.println("Montant invalide.");
        }
    }
}
```
### Explication :

### Héritage :
- `CompteEpargne` hérite de la classe `CompteBancaire`. Cela signifie que `CompteEpargne` possède tous les attributs et méthodes de `CompteBancaire`, en plus des siens propres.

### Attributs de la classe `CompteEpargne` :
- `taux` : Cet attribut représente le taux d'intérêt associé au compte épargne.

### Constructeur `CompteEpargne` :
- Il initialise un objet `CompteEpargne` avec les valeurs passées en paramètres, ainsi que les valeurs nécessaires héritées de `CompteBancaire`.

### Méthode `ajouterInteret()` :
- Cette méthode calcule et ajoute les intérêts au solde du compte épargne, en fonction du taux d'intérêt défini. Si le solde est positif, les intérêts sont calculés et crédités sur le compte.

### Méthode `decrire()` :
- Cette méthode retourne une chaîne de caractères décrivant le compte épargne. Elle affiche le numéro du compte, son solde, sa devise et son taux d'intérêt.

### Surcharge de méthode `debiter(float montant)` :
- Cette méthode surcharge la méthode `debiter(float montant)` de la classe parent `CompteBancaire`. La surcharge permet de modifier le comportement de la méthode pour les objets de la classe dérivée.
- Ici, la méthode `debiter(float montant)` vérifie si le montant à retirer est inférieur ou égal à la moitié du solde du compte. Si c'est le cas, elle effectue le retrait en appelant la méthode `debiter(float montant)` héritée de la classe parent. Sinon, elle affiche un message indiquant que l'opération est impossible.

# 3. Compte Courant
Faut créer une autre classe et l'appeler `CompteCourant` sont code est:

```Java
class CompteCourant extends CompteBancaire {
    private double decouvertMax; 
    
    public CompteCourant(String numero, Client titulaire, float solde, String devise, double decouvertMax) {
        super(numero, titulaire, solde, devise);
        this.decouvertMax = decouvertMax;
    }

    public String decrire() {
        return "Compte courant n°: " + getNumero() + " - solde : " + getSolde() + " " + getDevise() + " - Découvert max : " + decouvertMax + " " + getDevise();
    }

    public void debiter(float montant) {
        if (montant > 0) {
        	float nouveauSolde = getSolde() - montant;
            if (nouveauSolde >= -decouvertMax) {
                setSolde(nouveauSolde);
                System.out.println("Débit de " + montant + " " + getDevise() + " effectué.");
            } else {
                System.out.println("Opération impossible: le solde après débit dépasse le découvert maximal autorisé.");
            }
        } else {
            System.out.println("Montant invalide.");
        }
    }
}
```
### Explication  :

### Héritage :
- `CompteCourant` hérite de la classe `CompteBancaire`. Cela signifie qu'elle possède tous les attributs et méthodes de `CompteBancaire`, en plus de ses propres attributs et méthodes.

### Attributs de la classe `CompteCourant` :
- `decouvertMax` : Cet attribut représente le découvert maximal autorisé pour le compte courant.

### Constructeur `CompteCourant` :
- Il initialise un objet `CompteCourant` avec les valeurs passées en paramètres, ainsi que les valeurs nécessaires héritées de `CompteBancaire`.

### Méthode `decrire()` :
- Cette méthode retourne une chaîne de caractères décrivant le compte courant. Elle affiche le numéro du compte, son solde, sa devise et le découvert maximal autorisé.

### Surcharge de méthode `debiter(float montant)` :
- Cette méthode surcharge la méthode `debiter(float montant)` de la classe parent `CompteBancaire`. La surcharge permet de modifier le comportement de la méthode pour les objets de la classe dérivée.
- Ici, la méthode `debiter(float montant)` vérifie si le montant à retirer est valide et si le solde après le retrait ne dépasse pas le découvert maximal autorisé. Si les conditions sont remplies, le retrait est effectué, sinon un message d'erreur est affiché.
# Main

```Java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) throws ParseException {
        ArrayList<CompteBancaire> comptes = new ArrayList<CompteBancaire>();

        SimpleDateFormat simpleDateFormat = new SimpleDateFormat("dd/MM/yyyy");

        Client benjamin = new Client(
            "Gravouil",
            "Benjamin",
            true,
            simpleDateFormat.parse("02/05/1977"),
            "enseignant",
            "lycée Paul Lapie, 5 boulevard AB, 92400 COUR",
            "01.01.01.01.01",
            "prof.gravouil@gmail.com"
        );

        CompteBancaire compte1 = new CompteCourant("13245411324", benjamin, 2548200, "USD", 200);
        CompteBancaire compte2 = new CompteEpargne("32544771289", benjamin, 1000, "USD", 5);

        comptes.add(compte1);
        comptes.add(compte2);
        benjamin.setComptes(comptes);

        System.out.println("Comptes avant opérations :");
        for (CompteBancaire compte : benjamin.getComptes()) {
            System.out.println(compte.decrire());
        }
        System.out.println();

        System.out.println("Tests de retraits :");
        for (CompteBancaire compte : benjamin.getComptes()) {
            if (compte instanceof CompteCourant) {
                System.out.println("Compte courant :");
                System.out.println("Solde avant retrait : " + compte.getSolde());
                ((CompteCourant) compte).debiter(700);
                System.out.println("Solde après retrait : " + compte.getSolde());
            } else if (compte instanceof CompteEpargne) {
                System.out.println("Compte épargne :");
                System.out.println("Solde avant retrait : " + compte.getSolde());
                ((CompteEpargne) compte).debiter(600);
                System.out.println("Solde après retrait : " + compte.getSolde());
            }
            System.out.println();
        }

        System.out.println("Comptes après opérations :");
        for (CompteBancaire compte : benjamin.getComptes()) {
            System.out.println(compte.decrire());
        }

        for (CompteBancaire compte : benjamin.getComptes()) {
            if (compte instanceof CompteEpargne) {
                ((CompteEpargne)compte).ajouterInteret();
            }
        }

        System.out.println("\nAprès ajout des intérêts sur le compte épargne 32544771289:");
        for (CompteBancaire compte : benjamin.getComptes()) {
            System.out.println(compte.decrire());
        }
    }
}
```
### Explication :

### Importation des packages nécessaires :
- Le programme importe les packages nécessaires pour manipuler les dates (`java.text.SimpleDateFormat`), gérer les exceptions (`java.text.ParseException`) et utiliser des listes (`java.util.ArrayList`).

### Définition de la classe `Main` :
- La classe `Main` est la classe principale du programme.

### Méthode `main` :
- C'est la méthode principale exécutée lorsque le programme démarre.

### Création de la liste de comptes :
- Une liste `comptes` de type `ArrayList` de `CompteBancaire` est créée pour stocker les comptes bancaires.

### Création de clients :
- Un objet `SimpleDateFormat` est créé pour formater les dates.
- Un client `benjamin` est créé avec ses informations personnelles et stocké dans la variable `benjamin`.

### Création de comptes bancaires :
- Deux comptes bancaires sont créés (`compte1` et `compte2`) avec les informations nécessaires.
- Le premier compte est un compte courant et le second est un compte épargne.
- Ces comptes sont ajoutés à la liste des comptes du client `benjamin`.

### Affichage des comptes avant les opérations :
- Les informations de chaque compte de `benjamin` sont affichées avant les opérations.

### Tests de retraits :
- Une boucle parcourt chaque compte de `benjamin`.
- Si le compte est de type `CompteCourant`, un retrait est effectué de 700 USD.
- Si le compte est de type `CompteEpargne`, un retrait est effectué de 600 USD.
- Le solde est affiché avant et après chaque retrait.

### Affichage des comptes après les opérations de retrait :
- Les informations de chaque compte de `benjamin` sont affichées après les opérations de retrait.

### Ajout des intérêts sur les comptes épargne :
- Une boucle parcourt chaque compte de `benjamin`.
- Si le compte est de type `CompteEpargne`, les intérêts sont ajoutés au solde.

### Affichage des comptes après l'ajout des intérêts :
- Les informations de chaque compte de `benjamin` sont affichées après l'ajout des intérêts sur les comptes épargne.
