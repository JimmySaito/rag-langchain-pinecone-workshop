rag-langchain-pinecone-workshop

Workshop: Building a Retrieval-Augmented Generator (RAG) with LangChain, OpenAI, and Pinecone

Este repositorio contiene la implementación práctica de un taller diseñado para construir y desplegar un sistema de Generación Aumentada por Recuperación (RAG), utilizando modelos de lenguaje avanzados, embeddings y bases de datos vectoriales tanto locales como en la nube.

🛠️ Tecnologías y Librerías Utilizadas

Python 3.10+
LangChain (Orquestador de flujos y cadenas RAG mediante LCEL)
OpenAI API (gpt-4o-mini para generación y text-embedding-3-small para vectorización)
FAISS (Almacenamiento y búsqueda vectorial local en memoria)
Pinecone (Base de datos vectorial gestionada en la nube para alta escalabilidad)
Jupyter Notebook (Entorno de desarrollo interactivo)
📂 Estructura del Proyecto

rag-workshop/

├── data/

│ └── knowledge.txt # Base de conocimiento local utilizada para el contexto

├── .env # Variables de entorno (API Keys de OpenAI y Pinecone)

├── workshop_rag.ipynb # Jupyter Notebook principal con la implementación completa

└── README.md # Documentación del proyecto



-----------------------------------------------------------------------------

## Guía de Configuración e Instalación

Clonar el repositorio y configurar el entorno virtual


git clone [https://github.com/tu-usuario/rag-workshop.git](https://github.com/tu-usuario/rag-workshop.git)

cd rag-workshop

python -m venv venv





Activa el entorno virtual:



En Windows (CMD / PowerShell):



Bash

venv\Scripts\activate

En macOS / Linux:



Bash

source venv/bin/activate

2. Instalar las dependencias necesarias

Bash

pip install langchain langchain-openai langchain-community langchain-pinecone langchain-core pinecone-client python-dotenv faiss-cpu

3. Configurar las Variables de Entorno

Crea un archivo llamado .env en la raíz del proyecto y añade tus credenciales de forma segura:



Fragmento de código

OPENAI_API_KEY=tu_api_key_de_openai_aqui

PINECONE_API_KEY=tu_api_key_de_pinecone_aqui

---------------------------------------------------------------------------



Descripción de la Arquitectura y Fases del Taller

Parte 1: RAG Básico con FAISS (Local)

Carga y Fragmentación (Chunking): Lectura del archivo de conocimiento (data/knowledge.txt) utilizando TextLoader y división en fragmentos manejables mediante RecursiveCharacterTextSplitter.



Embeddings Locales: Transformación de texto a vectores de alta dimensión utilizando el modelo de OpenAI (text-embedding-3-small).



Recuperación y Generación: Indexación temporal en memoria con FAISS e implementación de una cadena RAG moderna basada en LCEL (LangChain Expression Language) junto con gpt-4o-mini.



Parte 2: RAG Escalable con Pinecone (Cloud)

Conexión Cloud: Migración del almacenamiento vectorial hacia Pinecone utilizando índices serverless optimizados con métrica de similitud de coseno (cosine).



Persistencia y Consultas: Indexación remota de documentos y recuperación eficiente de contexto a gran escala para alimentar de manera dinámica al modelo de lenguaje.



---------------------------------------------------------------------------------------

Ejecución del Notebook

Inicia Jupyter Lab o Jupyter Notebook en tu terminal:



Bash

jupyter lab



Abre el archivo workshop_rag.ipynb y ejecuta las celdas secuencialmente de arriba hacia abajo para replicar el pipeline completo de RAG local y en la nube.
