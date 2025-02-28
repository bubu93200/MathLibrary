#######################
# FONCTIONNE
#######################
# Essai basé sur MathLibrary
Exemple d'utilisation de la librairie dynamique MathLibrary pour le calcul des nombres de fibonacci.
Basé sur le tutoriel de Microsoft :   
https://learn.microsoft.com/fr-fr/visualstudio/debugger/debugging-dll-projects?view=vs-2022  
https://learn.microsoft.com/fr-fr/cpp/build/walkthrough-creating-and-using-a-dynamic-link-library-cpp?view=msvc-170  

# Explications du code
Les projets MathLibrary et MainMathLibrary sont des projets C++ créés avec Visual Studio 2022.   
- Le projet MathLibrary est une librairie dynamique qui contient une fonction pour calculer les nombres de fibonacci.  
- Le projet MainMathLibrary est une application console qui utilise la librairie MathLibrary pour calculer les nombres de fibonacci.

# Projet MathLibrary
Le projet MathLibrary est une librairie dynamique qui contient une fonction pour calculer les nombres de fibonacci.
Il suffit de compiler le projet MathLibrary pour obtenir le fichier MathLibrary.dll. 
On aura besoin des fichiers suivants pour l'application console : 
- C:\Users\bubu\source\repos\MathLibrary\x64\Debug\MathLibrary.dll
- C:\Users\bubu\source\repos\MathLibrary\MathLibrary\x64\Debug\MathLibrary.obj
- C:\Users\bubu\source\repos\MathLibrary\MathLibrary\MathLibrary.h

TODO : Vérifier pour .obj et .dll ? ou .lib ?

# Projet MainMathLibrary
Le projet MainMathLibrary est une application console qui utilise la librairie MathLibrary pour calculer les nombres de fibonacci.

## Configuration du projet MainMathLibrary dans Visual Studio 2022
- Ajouter le chemin du projet MathLibrary dans les propriétés du projet MainMathLibrary :   
  - Propriétés du projet MainMathLibrary -> C/C++ -> Général -> Répertoires Include supplémentaires :   
	- C:\Users\bubu\source\repos\MathLibrary\MathLibrary
  - Propriétés du projet MainMathLibrary -> Lien -> Général -> Répertoires de bibliothèques supplémentaires :   
	- C:\Users\bubu\source\repos\MathLibrary\x64\Debug
  - Propriétés du projet MainMathLibrary -> Lien -> Entrée -> Dépendances supplémentaires :   
	- MathLibrary.lib

