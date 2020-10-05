
# simulation épidémiologique 
<br/>

[![Codacy Badge](https://api.codacy.com/project/badge/Grade/1be197d831a742f5af9d86e04a70721f)](https://app.codacy.com/manual/antoninlefevre45/simulation_virus_covid-19?utm_source=github.com&utm_medium=referral&utm_content=antonin-lfv/simulation_virus_covid-19&utm_campaign=Badge_Grade_Dashboard)

Article lié à ce github : ( à venir )

Ce projet à pour objectifs de créer un virus, et de simuler sa propagation au sein d'une population. Les individus infectés pourront transmettre le virus avec une certaine probabilité, et peuvent aussi devenir immunisés ou bien décéder. 
En utilisant les paramètres propres du covid-19 on peut modeliser grossièrement ce dernier.

On choisira des populations de quelques dizaines à quelques milliers d'individus et on supposera qu'un individu immunisé ne peut plus être infecté.
Cette modélisation sera réalisée avec matplotlib puis avec plotly dans 2 fichiers différents.
<br/><br/>

## Exemple de résultats sous plotly 

<br/>

![simulation](https://user-images.githubusercontent.com/63207451/87425516-11c8b800-c5de-11ea-855a-641e82b8ee96.png)
<br/><br/>

## Librairies 

<br/>
Si vous n'avez jamais utilisé plotly pensez à le télécharger via la console :


	pip install plotly


Documentation plotly: <https://plotly.com/python/>

A chaque exécution d'une fonction sous plotly, une page html s'ouvrira avec le résultat.

Pour matplotlib une simple fenêtre python apparaîtra (ou plus).
<br/><br/>

## Simulation de la propagation

<br/>
Lors de la simulation, plusieurs paramètres peuvent être changés.

Vous pouvez selectionner :
  
		• nb_population : le nombre d'individus au départ. 

Ce chiffre peut varier entre 0 et 2000 pour optimiser le temps d'éxecution.<br/><br/>
  
		• variance_population : pour avoir une population plus ou moins étalée. 

Elle variera entre 0 et 10 pour des populations inférieures à 2000 individus.<br/><br/>
 
 		• rayon_contamination : qui détermine le rayon dans lequel un individu infecté peut infecter un individu sain. 

Il devra être choisi en fonction de la variance, pour éviter l'arrêt prématuré de la simulation.<br/><br/>
  
		• infectiosité : probabilité qu'un infecté transmette le virus dans son rayon de contamination. 

Probabilité compris entre 0 et 1, à choisir selon le degrés d'infectiosité de l'épidémie à simuler.<br/><br/>

		• p : probabilité qu'une personne infectée devienne immunisée. 
	
Probabilité entre 0 et 1, qui détermine si les individus peuvent résister à l'épidémie.<br/><br/>
	  
		• d : probabilité qu'une personne infectée décède.    

Pribabilité comprise entre 0 et 1, qui renseigne sur la létalité du virus.<br/><br/>

Au début de chaques fonctions, des paramètres vous sont recommandés pour profiter au mieux du résultat. 
<br/><br/>

## Simuler un confinement 

<br/>
On peut également simuler un confinement de la population, en diminuant la variance de celle-ci et en augmentant le nombre de centres.<br/>

Par exemple avec les paramètres :

	nb_population = 1200
	
	variance_population = 1
	
	centers = 7 ( dans la fonction make_blobs de l'algorithme )
	
	rayon = 2
	
	infectiosité = 0.7
	
	p = 0.4
	
	d = 0.3

<br/>

On obtient la simulation suivante :

![confinement](https://user-images.githubusercontent.com/63207451/95127775-d5c66e80-0758-11eb-9a50-2f7285ea596f.png)

<br/>

Les autres paramètres peuvent être évidemment changés.

