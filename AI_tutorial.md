# VectorShift: 
Abonnement 25 €/mois (permet plusieurs pipelines et intégration Knowledge Base) :abonnement pris le 6/2/2025
## Création d'agents avec [VectorShift](https://www.youtube.com/watch?v=7sgibmj_MBY) : ✅
débutant (le faire sans le RAG , l'implantation suit). L'interface a été mis à jour le 3 février 2025
## [RAG agent avec VectorShift](https://www.youtube.com/watch?v=ieLdMih5_V0) ✅
## [Parler à son agent de sa base de connaissance](https://www.youtube.com/watch?v=7sgibmj_MBY)  ✅
## [Argentic agent avec R1](https://www.youtube.com/watch?v=uWDocIoiaXE&t=254s) ✅
![Architecture](https://raw.githubusercontent.com/jpbrasile/images/refs/heads/main/Capture%20d'%C3%A9cran%202025-02-07%20091925.png)

- [Ici](https://github.com/coleam00/ottomator-agents/tree/main/r1-distill-rag) pour la mise en oeuvre
-  Nous disposons de deux llm , l'un qui réfléchit et fait les requ^tes RAG, le cas échéant modifiant la requête si le résultat est insuffisant, l'autre mettant en forme la réponse à la question.
- L'intérêt d'utiliser Ollama est que l'on peut adapter la taille du contexte du llm en deux lignes de code
```
FROM qwen2.5:7b-instruct-q4_K_M
PARAMETER num_ctx 8096
```
## [Pour "scraper" un site internet](https://www.youtube.com/watch?v=c5dw_jsGNBk&t=795s)

- L'objectif est d'utiliser Crawl4AI, un scraper rapideet facile d'emploi et l'insérer dans un workflow n8n. 
- Crawl4AI est à la base une  bibliothèque python. Pour l'adapter à n8n nous allons la faire "tourner" dans un container docker, deployée sur DigitalOcean pour y avoir accès par API.
- DigitalOcean permet de configurer des machines virtuelles, elles peuvent être mise en sommeil avec les [snapshots](https://docs.digitalocean.com/products/snapshots/getting-started/quickstart/) 
