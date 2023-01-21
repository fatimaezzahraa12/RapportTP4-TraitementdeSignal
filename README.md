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


  
  
  
  


      
       
      
