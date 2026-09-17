# 🌌 Dungeon Graph Studio

O **Dungeon Graph Studio** é uma ferramenta de geração procedural de masmorras espaciais desenvolvida em **GameMaker (GML)**. O projeto aplica conceitos formais de **Teoria dos Grafos** para garantir que cada mapa gerado seja matematicamente solvável, eliminando problemas clássicos de *game design* como *softlocks*, ilhas isoladas e caminhos sem saída.

---

## 🛠️ Conceitos de Grafos Aplicados

- **Modelagem de Masmorra:** 
  - **Vértices ($V$):** Representam as salas/planetas (`obj_sala`).
  - **Arestas ($E$):** Representam os corredores e rotas espaciais entre os planetas.
  - **Dígrafos:** Utilizados em salas de desafios/mini-bosses com caminhos unidirecionais.
- **Estrutura de Dados:** **Lista de Adjacência** (`ds_map` + `ds_list`), otimizando o uso de memória em complexidade $O(V + E)$ por se tratar de um grafo esparso.
- **Métrica de Peso:** **Distância de Manhattan** ($d = \vert{}\Delta x\vert{} + \vert{}\Delta y\vert{}$), ideal para o cálculo de peso das arestas em grades ortogonais.
- **Validação de Solvabilidade (BFS):** O algoritmo de **Busca em Largura** verifica em tempo linear se a Saída é alcançável a partir da Entrada, identificando e destacando ilhas desconectadas.
- **Caminho Crítico (Dijkstra):** Calcula a menor rota garantida respeitando dependências lógicas do jogo ($\text{Entrada} \rightarrow \text{Chave} \rightarrow \text{Tranca} \rightarrow \text{Chefe}$).
- **Topologia Planar ($g = 0$):** Garante a renderização do mapa em um plano 2D sem sobreposição de corredores/arestas.

---

## 🕹️ Controles e Modos Interativos

| Tecla | Ação / Funcionalidade |
| :---: | :--- |
| **`[R]`** | Gera uma nova **Dungeon Procedural** a partir de uma *seed* aleatória. |
| **`[M]`** | Gera o modo **Overworld / Super Zona** (grade expansiva $5 \times 4$). |
| **`[1]`** | Alterna a exibição das **Arestas do Grafo Base** (linhas de conexão). |
| **`[3]`** | Alterna a exibição do **Caminho Crítico / Dijkstra** (linha amarela). |
| **`[S]`** | Permite inserir manualmente uma **Seed** customizada. |
| **`[F]`** | Simula uma **Falha de Geração** para demonstrar o algoritmo de detecção de nós isolados. |
| **`[TAB]`** | Ativa/Desativa o **Modo Raio-X** (exibe IDs dos vértices para depuração). |

---

## 💻 Tecnologias Utilizadas

* **Engine:** GameMaker Studio 2
* **Linguagem:** GameMaker Language (GML)
* **Paradigma Algorítmico:** Teoria dos Grafos & Geração Procedural Ponderada

---

## 👥 Autores

* **João Pedro Moraes**
* **Hermes Tupinambá**
* **José Scaff**
