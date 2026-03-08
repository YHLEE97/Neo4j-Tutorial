# Neo4j-GraphRAG 튜토리얼 🚀

이 프로젝트는 **Neo4j 그래프 데이터베이스**와 **LLM (LangChain, OpenAI, Google Gemini)**을 결합하여 GraphRAG(Graph Retrieval-Augmented Generation) 시스템을 단계별로 구축하고 실습하기 위한 노트북(코드) 모음입니다.

기본적인 Neo4j 환경 설정 및 Cypher 쿼리 작성법부터, Text2Cypher(자연어를 쿼리로 변환), 그리고 최종적으로 비정형 텍스트(뉴스 기사)를 분석해 스스로 지식 그래프(Knowledge Graph)를 구축하는 고급 실습까지 포함되어 있습니다.

---

## 📁 주요 내용 (Contents)

### Part 1: Neo4j 기본 지식 및 영화(Movie) 데이터 활용 실습 🎬
이 파트에서는 이미 정형화된 영화 관련 데이터를 통해 그래프 데이터베이스의 기본기를 다집니다.

- `KG_P1_01_neo4j_Introduction.ipynb`: Neo4j 소개, 기본 개념 및 환경 설정
- `KG_P1_02_neo4j_cypher_advanced.ipynb`: 데이터 조작 및 고급 Cypher 쿼리 작성법
- **검색 및 AI 애플리케이션 연동:**
  - `03_neo4j_movie_01_csv.ipynb`: CSV 파일을 Neo4j로 데이터 임포트
  - `03_neo4j_movie_02_basic_search.ipynb`: 노드/관계 기반 기본 검색 로직
  - `03_neo4j_movie_03_full-text_search.ipynb`: 전문 검색(Full-text search) 인덱스 활용
  - `03_neo4j_movie_04_vector_search.ipynb`: Vector DB로서의 Neo4j를 활용한 임베딩 유사도 검색
  - `03_neo4j_movie_05_text2cypher.ipynb`: LLM을 이용해 사용자의 자연어 질문을 직접 Cypher 쿼리로 변환 (Text-to-Cypher)
  - `03_neo4j_movie_06_graphRAG.ipynb`: 그래프 검색과 벡터 검색을 융합한 GraphRAG 최종 구현

### Part 2: LLM을 활용한 지식 그래프 추론 및 구축 실습 📰
이 파트에서는 비정형 데이터에서 유의미한 정보를 뽑아내 데이터베이스를 구축하는 방법을 배웁니다.

- `KG_P2_01_news_analysis.ipynb`: 비정형 텍스트(뉴스 기사) 데이터에서 LLM (LangChain `LLMGraphTransformer`)을 활용하여 자체적으로 주체(Entity)와 관계(Relationship)를 추출하고 Neo4j 데스크탑에 지식 그래프를 새롭게 구성하는 실습 

---

## 🛠 필수 조건 및 환경 설정 (Setup)

### 1. 의존성 (패키지) 설치
이 프로젝트는 Python 3.12 이상의 환경이 필요하며, 패키지 및 가상환경 관리는 빠르고 현대적인 **[uv](https://github.com/astral-sh/uv)** 를 통해 이루어집니다.

```bash
# 빠른 의존성 설치 및 가상환경(.venv) 자동 구성
uv sync
```
*참고:* 기존 `pip` 환경 사용자도 `uv pip install -r pyproject.toml` 명령어로 호환 가능합니다.

### 2. 환경 변수 설정 (`.env`)
프로젝트 루트 경로에 있는 `env.sample` 파일의 이름을 `.env`로 변경하거나 새로 생성한 뒤, 아래와 같이 API 키 및 접속 정보를 입력해주세요.

```ini
OPENAI_API_KEY=sk-본인의_오픈AI_키입력
GOOGLE_API_KEY=AIzaSy_본인의_구글API_키입력

# 연결할 Neo4j 정보 작성 (로컬 데스크탑의 경우)
NEO4J_URI=bolt://localhost:7687
NEO4J_USERNAME=neo4j
NEO4J_PASSWORD=본인비밀번호
NEO4J_DATABASE=neo4j
```

---

## 💻 주요 기술 스택 (Tech Stack)
- **Database**: Neo4j (Local Desktop 또는 AuraDB)
- **LLM / AI**: OpenAI (gpt-4o), Google GenAI, LangChain 
- **Language**: Python 3.12
- **Environment**: Jupyter Notebook (VSCode)
