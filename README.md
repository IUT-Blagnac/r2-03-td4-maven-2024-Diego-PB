# Diego Penicaud-Bernal
## BUT1 Informatique / Groupe 4A

<hr>

# Compilation n°1 :

<h2>Commandes éxécutés :</h1>

| Commande | explication          |
| :--------------- |:---------------:|
| mvn clean  |   Nettoye ce qu'il s'est passé avant.        |
| mvn compile  |  Compile les classes : création du répertoire target qui contient ensuite la version compilée des classes (target/classes).             |


<hr>

# Compilation n°2 :


<h3>Code du main :</h3>

```java
public static void main(String[] args) {
		System.out.println("Hello Blagnac");
	}
```



<h2>Commandes éxécutés :</h1>

| Commande | explication          |
| :--------------- |:---------------:|
| mvn package  |   Crée une version éxécutable des classes compilées.        |
| java -jar target/tp_qualite-1.0.jar  |   Exécute cette nouvelle version éxécutable.           |




# Améliorations


<h3>Reprise d'un exercice :</h3>

```java

public class Exo {
	public static void main(String[] args) {
		System.out.println("1, 2, 3");
        afficher();
	}

    public static void afficher() {
        System.out.println("Bonjour");
    }
}
```


<h3>Ajustement du fichier pom.xml :</h3>


```xml
<plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-jar-plugin</artifactId>
            <configuration>
                <archive>
                    <manifest>
                        <mainClass>HelloJava</mainClass> 
                    </manifest>
                </archive>
            </configuration>
        </plugin>
```

<p> devient :

```xml
<plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-jar-plugin</artifactId>
            <configuration>
                <archive>
                    <manifest>
                        <mainClass>Exo</mainClass> 
                    </manifest>
                </archive>
            </configuration>
        </plugin>
```



<h3>Génération de la documentation</h3>

<p> Pour générer la Javadoc de manière automatique il faut ajouter ce code au fichier xml :

```xml
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-javadoc-plugin</artifactId>
            <version>3.3.2</version>
            <configuration>
                <source>1.8</source> 
                <doclint>none</doclint> 
            </configuration>
        </plugin>
```
<p>Il faut ensuite ajouter la javadoc avec 'mvn javadoc:javadoc' ensuite compiler avec 'mvn compile', puis créer une version éxécutable avec 'mvn package'.
