# RapportTP4-TraitementdeSignal

Réalisé par :Fatima Ezzahraa Chadni

# Thème :Filtrage Analogique des signaux.
  -Objectifs:
  -Appliquer un filtre réel pour supprimer les composantes indésirables d’un signal. 
  -Améliorer la qualité de filtrage en augmentant l’ordre du filtre.
  
-Travail Demandé: Réaliser un script Matlab commenté qui contient le travail réalisé avec les représentations graphique expliquées sur le travail Effectué.

# Manipulation 1:Filtrage et diagramme de Bode.
    Mathématiquement, un tel filtre fournit un signal de sortie en convoluant le signal 
    d'entrée par la réponse temporelle du filtre :
         y(t) = x(t) * h(t)
   On souhaite appliquer un filtre passe-haut pour supprimer la composante à 50 Hz de notre signal. Soit notre signal d'entrée :
      x(t) = sin(2.pi.f1.t) + sin(2.pi.f2.t) + sin(2.pi.f3.t),avec les valeurs de fréquence sont respectivement:f1 =         500 Hz, f2 = 400 Hz et f3 = 50 Hz.
      On commence par définir notre signal avec un période d'échantillonnage Te=0.0001s .
      L'intervalle de temps est défini comme t=0:Te:5-Te .
      le nombre d'échantillons est défini comme N=length(t).
      on définit aussi l'intervalle de fréquence fshift qui permet de centrer le spectre fréquentiel par rapport à l'axe des ordonnées.
      La transformée de Fourrier de notre signal se calcule par le biais de la commande fft().
      ![image](https://user-images.githubusercontent.com/120644217/213882934-7f9d13c6-d6db-4107-b148-c76366d0da5d.png)
      # Représentation temporelle du signal.
      ![image](https://user-images.githubusercontent.com/120644217/213883228-0927df84-74a0-4d72-9797-42b2f3d0d5c3.png)
      Représentation fréquentielle du signal.
      ![image](https://user-images.githubusercontent.com/120644217/213883291-c2675a0d-299a-4d2c-ab6d-48e4b0c085ed.png)
      
  # Représentation du diagramme de Bode.
  À ce stade,on passe à tracer le diagramme de bode dans les trois cas qu'on va tester.
  On va utiliser trois valeurs de fréquences dont les valeurs sont respectivement f1=250Hz,f2=500Hz,f3=1000Hz,puis on passe à calculer la valeur de la  transmittance     complexe pour chacune des valeurs citées.

  
  ![image](https://user-images.githubusercontent.com/120644217/213883839-ecfc1f3d-1064-4cd7-ae97-64a7e3df3c84.png)
  
  Module de la transmittance complexe.
  
  ![image](https://user-images.githubusercontent.com/120644217/213884043-e2a68cff-cd58-4a59-aba3-94338371cc53.png) 
  
  ![image](https://user-images.githubusercontent.com/120644217/213884252-12433e4b-3e70-48dc-a783-7e9123dc2fba.png)
  
  # Représentation graphique pour les trois valeurs de fréquence choisies.
  
  ![image](https://user-images.githubusercontent.com/120644217/213884381-51716c9c-a764-4b26-abde-14b70e64d315.png)
  
  # Débruitage d'un signal sonore.
  
  À travers cette manipulation,notre objectif est d'éliminer le bruit de notre signal qui représente une musique.
  La première étape à faire est de tracer le spectre fréquentiel du signal pour visualiser la gamme de fréquences à eliminer pour débruiter notre signal ainsi que       classer notre fréquence pour savoir si c'est une faible ou haute fréquence.
  On commence par lire notre fichier qui contient le signal à traiter par la commande audioread() , ceci pour récupérer l'ensemble des valeurs qui le constituent .
  On définit ensuite le nombre d'échantillons ainsi que la période et la fréquence d'échantillonnage pour appliquer la transformée de fourrier au signal.
  
  ![chrgermusic](https://user-images.githubusercontent.com/120644217/213918965-bc7ae1a7-93ed-45f4-8045-61234da609ec.PNG)
  
   La figure représentée ci-dessous illustre le spectre fréquentiel de notre signal.
   
   ![spectre musqiue](https://user-images.githubusercontent.com/120644217/213919021-5e711664-8f8c-4b1b-93ba-c2c91e370ca1.PNG)
   
   Comme on peut observer dans la figure,la fréquence 5124Hz représente la fréquence qu'il faut éliminer du signal ,c'est cette valeur de fréquence qui rend notre        signal bruité.
   Après avoir connu la fréquence à eliminer ,on passer à l'étape suivante,qui est le filtrage.
   Pour ce faire, on commence par faire la conception du filtre et choisit pour un premier test une fréquence de coupure fc=4500Hz.
   On définit l'expression de notre filtre en exploitant la transmittance complexe,puis on l'applique à notre spectre fréquentiel de musique.
   
   ![filtremusic1](https://user-images.githubusercontent.com/120644217/213919489-806efd73-a8d3-4806-8929-6fe02fcdf793.PNG)
   
   On représente dans la figure ci-dessous  le module de la transmittance complexe associée à ce filtre, pour savoir si le choix de la fréquence de coupure est aussi      bon pour débruiter le signal.
   
   ![moduleH](https://user-images.githubusercontent.com/120644217/213919735-a4a83e9d-500b-4159-9473-f86142026822.PNG)
    
   le code qui permet de tracer cette figure est représentée ci-dessous:
   
   ![moduleFiltre](https://user-images.githubusercontent.com/120644217/213919774-3140e370-8153-4898-a0ed-7f2be990343e.PNG)
   
   La fréquence choisir ne permet pas d'atteindre un bon filtrage de notre signal,donc la prochain test va englober le changement de la fréquence de coupure ainsi que    l'ordre du filtre qui permet de garantir un bon filtrage.
   La nouvelle fréquence de coupure est de l'ordre de fc=5000Hz.
   La valeur de l'ordre du filtre choisi est n=1000.
   
   ![filtre2musique](https://user-images.githubusercontent.com/120644217/213920161-1fdaf5ea-0856-4b20-a360-753cb3c14e08.PNG)
   
   -Le module de la transmittance complexe associée à ce filtre est représentée dans la figure ci-desous:
   
   ![filtre2](https://user-images.githubusercontent.com/120644217/213920247-56d9db28-0ce3-4328-96e7-405e0f812e9b.PNG)
   
   Ces nouveaux paramètres de fréquence de coupure <fc> ainsi que l'ordre du filtre <n> permettent de se rapprocher rapidement à la forme d'un filtre idéal.Ceci nous      permet de garantir le meilleur filtrage de notre signal.
   Et de cette manière,on a pu débruiter d'une façon optimale notre signal .
    
