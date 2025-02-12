# Un bon assistant, c'est quoi ?
- Il vous aide à bien formuler vos questions
- Il cherche les réponses
  - après y avoir réfléchi
  - en faisant des recherches approfondies sur le web
  - en n'hésitant pas à utiliser des outils pour mieux y répondre, ainsi il est parfois plus facile de créer et d'exécuter un code pour y répondre
  - il organise les données recueillies en un ensemble cohérent (graphe sémantique)
  - il "digère" le savoir nécessaire à assurer son expertise
 
Voir cette [publication](https://www.researchgate.net/publication/388847740_Agentic_Reasoning_Reasoning_LLMs_with_Tools_for_the_Deep_Research) d'Oxford qui montre l'intérêt d'intégrer à la fois, le raisonnement à des outils (recherche web, codage) pour obtenir de meilleurs résultats. Le code n'est pas encore publié.   

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
- L'intérêt d'utiliser Ollama est que l'on peut adapter la taille du contexte du llm en deux lignes de code que 'on met dans Modelfile
```
FROM qwen2.5:7b-instruct-q4_K_M
PARAMETER num_ctx 8096
```
puis 
```
ollama create qwen2.5-128k -f Modelfile
```
## [Pour "scraper" un site internet](https://www.youtube.com/watch?v=c5dw_jsGNBk&t=795s)

- L'objectif est d'utiliser Crawl4AI, un scraper rapide et facile d'emploi et l'insérer dans un workflow n8n. 
- Crawl4AI est à la base une  bibliothèque python. Pour l'adapter à n8n nous allons la faire "tourner" dans un container docker, deployée sur DigitalOcean pour y avoir accès par API.
- DigitalOcean permet de configurer des machines virtuelles, elles peuvent être mise en sommeil avec les [snapshots](https://docs.digitalocean.com/products/snapshots/getting-started/quickstart/)

## [Deep research](https://www.youtube.com/watch?v=cUsSAxwEs8Y&t=117s) ✅ (installé sur Docker) 
- OpenAI propose pour 200$/mois, 100 requêtes de recherche web. On peut faire l'équivalent avec browser-use/web ui
- Une [installation en local](https://github.com/browser-use/web-ui), sous Docker ou non est possible. La video suggère d'utiliser l'API sambanova avec une variante distillée de R1:


- Avec l'API de Google et gemini2.0 flash thinking on obtient [milk_pasteurization.md](https://github.com/jpbrasile/AtTheSameTime/blob/main/milk_pasteurization.md) avec une requête sur l'état de l'art de l'utilisation des plasmas froids pour le traitement du lait. 
- Nous avons réalisé un [teaser](https://jpbrasile-milk_cap_pasteurization.web.val.run) avec Townie (Val Town). Le point dur a été de lui faire maîtriser la durée de la voix, une astuce a alors été de lui demander 5 options possibles pour qu'il arrête de tourner en rond sans répondre au besoin de synchronisation (MediaRecorder a été choisi)

### Une [alternative avec firecrawl](https://github.com/dzhng/deep-research) ✅ (installée avec npm) 
### Autres alternative Storm (standford) et Google Deep search 
```
"LLM Provider" --> "openai"
"Model Name"  --> "DeepSeek-R1-Distill-Llama-70B"
"Base URL" --> "https://api.sambanova.ai/v1"
```
