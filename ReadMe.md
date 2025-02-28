#######################
# FONCTIONNE
#######################
# Essai bas� sur MathLibrary
Exemple d'utilisation de la librairie dynamique MathLibrary pour le calcul des nombres de fibonacci.
Bas� sur le tutoriel de Microsoft :   
https://learn.microsoft.com/fr-fr/visualstudio/debugger/debugging-dll-projects?view=vs-2022  
https://learn.microsoft.com/fr-fr/cpp/build/walkthrough-creating-and-using-a-dynamic-link-library-cpp?view=msvc-170  

# Explications du code
Les projets MathLibrary et MainMathLibrary sont des projets C++ cr��s avec Visual Studio 2022.   
- Le projet MathLibrary est une librairie dynamique qui contient une fonction pour calculer les nombres de fibonacci.  
- Le projet MainMathLibrary est une application console qui utilise la librairie MathLibrary pour calculer les nombres de fibonacci.

# Projet MathLibrary
Le projet MathLibrary est une librairie dynamique qui contient une fonction pour calculer les nombres de fibonacci.
Il suffit de compiler le projet MathLibrary pour obtenir le fichier MathLibrary.dll. 
On aura besoin des fichiers suivants pour l'application console : 
- C:\Users\bubu\source\repos\MathLibrary\x64\Debug\MathLibrary.dll
- C:\Users\bubu\source\repos\MathLibrary\MathLibrary\x64\Debug\MathLibrary.obj
- C:\Users\bubu\source\repos\MathLibrary\MathLibrary\MathLibrary.h

TODO : V�rifier pour .obj et .dll ? ou .lib ?

# Projet MainMathLibrary
Le projet MainMathLibrary est une application console qui utilise la librairie MathLibrary pour calculer les nombres de fibonacci.

## Configuration du projet MainMathLibrary dans Visual Studio 2022
- Ajouter le chemin du projet MathLibrary et la d�pendance vers la biblioth�que dans les propri�t�s du projet MainMathLibrary :   
  - Propri�t�s du projet MainMathLibrary -> C/C++ -> G�n�ral -> R�pertoires Include suppl�mentaires :   
	- C:\Users\bubu\source\repos\MathLibrary\MathLibrary
  - Propri�t�s du projet MainMathLibrary -> Lien -> G�n�ral -> R�pertoires de biblioth�ques suppl�mentaires :   
	- C:\Users\bubu\source\repos\MathLibrary\x64\Debug
  - Propri�t�s du projet MainMathLibrary -> Lien -> Entr�e -> D�pendances suppl�mentaires :   
	- MathLibrary.lib

## Configuration du projet MainMathLibrary dans Visual Studio 2022 suppl�mentaire
***Je n'ai pas fait cette �tape et �a fonctionne quand m�me.***

Microsoft indique qu'il faut ajouter une commande xcopy pour copier le fichier MathLibrary.dll dans le r�pertoire de sortie de l'application console :
:
- Dans le volet gauche, s�lectionnez �v�nements>de g�n�ration de propri�t�s>de configuration apr�s l��v�nement de build.
- Dans le volet de propri�t�s, s�lectionnez le contr�le d��dition dans le champ Ligne de commande. Si vous avez suivi les instructions pour placer votre projet client dans une solution distincte du projet DLL, entrez cette commande :
- xcopy /y /d "..\..\MathLibrary\$(IntDir)MathLibrary.dll" "$(OutDir)"



# D�bogage
***Je n'ai pas fait cette �tape et �a fonctionne quand m�me.***

Pour d�boguer le projet MainMathLibrary, il faut ajouter la directive /ASSEMBLYDEBUG.
- Propri�t�s du projet MainMathLibrary -> propri�t�s de configuration -> Editeur de Lien -> D�bogage : 
    - Assembly pouvant �tre d�bogu� -> OUI /ASSEMBLYDEBUG



