Prépa exam
========================

Exam en deux parties : 

- Questions de cours
- Étude de cas

## Exercice d'entraînement

Une entreprise de 1000 personnes avec un CA de 200 M€ travaille dans la métallurgie. Le budget informatique est évalué à 1,4% du CA. Le système interne est composé d'un VAX VMS de 35 ans d'âge avec deux personnes dédiées. Ce système coûte 450K€ de maintenance et 280K€ de TMA et compte 250 utilisateurs. On estime une augmentation de 5% par an pour la maintenance et une augmentation de 10%/an pour la TMA. 

Le projet de la société est de changer ce système par un ERP appelé MANUSOFT. Le coût licence sera de 2000€/utilisateur avec 20% de maintenance/an sauf la première année. Le système est basé sur une base ORACLE à payer en plus : 20K€/OS/CPU. Avec 22% de maintenance/an. Dans notre calcul on prendra en compte 50 utilisateurs/CPU (plus un pour le fun). Nous avons une enveloppe 300 000 pour la personnalisation ,250 000 pour le paramétrage, 125K€ pour la repirse des données. Trois environnements : dev, test et prod. 
Le prix de licence de l'environnement de dev correspond à 50% du prix list. Environnemnts dev et test n'auront que 25 utilisateurs. 

Voici les tarfis : junior : 500/jour; 1000/jour pour senior et chef de projet, 1500/jour pour expert.

Calculer le budget sur trois ans et voir si il y a un ROI par rapport à si on ne fait rien. 

Budget IT : 2 800 000/an

Système actuel, cout :   

An 1 : 450 000 + 280 000 = 730 000  
An 2 : 472 500 + 308 000 = 780 500  
An 3 : 496 125 + 338 800 = 834 925  

Total sur 3 ans :  2 345 425

ERP, coût :

Coût licence :  2 000 * 250+ 20% (sauf an 1)  
An 1 : 500 000  
An 2 : 600 000  
An 3 : 600 000  

Coût Oracle : 20 000 * 6 + 22%  
An 1 : 146 400  
An 2 : 146 400  
An 3 : 146 400  

Soit :  
An 1 :  646 400  
An 2 : 746 400  
An 3 : 746 400


### Correction

Bon déjà il s'est planté sur le budget du voeux truc en inversant ls pourcentages.

**Coût des licences : **  
An 1 : 500 000  
An 2 : 600 000  
An 3 : 600 000  



Tout est en K€ 

| Désignation | Investissement | CPF (jours * ??) | Mainenance |
|----|----|----|----|
| HN - Serveur prod | 80 | 4 * 1 500 | 8 |
| Servueur dev&test | 10 | 2 * 1 500 | 1 |
| Self ERP | 500 | 5 * 1 500 | 0 |
| Self Oracle Prod | 120 | 2 * 1 500 | 26,4 |
| Self Oracle Dev/test | 20 | 2 * 1 500 | 4,4 |
| Custo | | 300 | |
| Paramétrage | 250 |  | |
| Données |  | 125 |  |
| Formation admin |  | 10 * 1 |  |
| Formation user |  |  |  |
