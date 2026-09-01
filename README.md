### Guia para criação de Jornadas e Collectibles

#### Jornada

Cada jornada deve seguir esta estrutura:

```json
{
	"table": "journey",
	"content": {
		"name": "Nome curto da jornada",
		"category": "Categoria",
		"course": "Curso relacionado",
		"description": "Descrição clara e objetiva do objetivo da jornada.",
		"image": "/images/journeys/nome-da-jornada.webp"
	},
	"depends": []
}
```

Regras:

* `name`: curto e direto.
* `description`: explicar claramente o objetivo da jornada.
* `depends`: usar apenas quando a jornada realmente depender de outra.
* `image`: **2848x1494 px**.
* Todas as imagens de jornadas devem manter **o mesmo estilo visual**.
* Otimizar as imagens para evitar consumo desnecessário do limite de **1 GB do repositório**.

#### Collectible

Cada artefato deve seguir a estrutura já definida:

```json
{
	"table": "collectible",
	"content": {
		"name": "Nome do artefato",
		"description": "Descrição informativa do artefato.",
		"image": "/images/collectibles/nome-do-artefato.webp",
		"props": {
			"model": "/models/collectibles/nome-do-artefato.glb",
			"AR": {
				"scale": "0.05 0.05 0.05",
				"position": "0 0 0",
				"rotation": "0 0 0",
				"zoom": "0.1"
			},
			"3D": {
				"scale": "0.05 0.05 0.05",
				"position": "0 0 0",
				"rotation": "0 0 0",
				"zoom": "0.1"
			}
		},
		"riddle": "Charada curta sobre o artefato.",
		"gpsLocation": "",
		"link": "",
		"credits": "",
		"points": "10",
		"journey": "Nome da jornada",
		"question": {
			"question": "Pergunta relacionada ao conteúdo apresentado.",
			"option_a": "Alternativa A",
			"option_b": "Alternativa B",
			"option_c": "Alternativa C",
			"option_d": "Alternativa D",
			"correct_option": "Alternativa correta",
			"fonte_link": "",
			"collectible": "Nome do artefato"
		}
	}
}
```

Regras principais:

* `description`: **máximo de 377 caracteres**.
* Deve ser curta, informativa e adequada ao nível dos alunos.
* Pode apresentar conceitos, diferenças entre tecnologias, fabricantes, gerações e compatibilidade quando forem relevantes.
* `riddle`: curta, relacionada diretamente ao artefato.
* `question`: deve verificar algum conhecimento apresentado na descrição ou durante a coleta.
* `points`: definir conforme a importância do artefato.

### Arquivos dos artefatos

**Modelo 3D**

* Formato obrigatório: `.glb`
* Tamanho máximo: **3 MB**
* Priorizar modelos simples e otimizados.
* Não usar modelos excessivamente detalhados quando um modelo mais simples transmitir o mesmo conceito.

**Imagem**

* Resolução: **526x474 px**
* Fundo: **transparente**
* Formato recomendado: `.png`
* Para collectibles, podem ser utilizadas **fotografias reais**.
* Quando for utilizada fotografia, o fundo deve ser removido ou tratado para manter o padrão visual esperado.
* Comprimir a imagem sem prejudicar sua identificação.

### Regra geral de conteúdo

A jornada apresenta o **objetivo geral**.

O collectible apresenta **o componente e seu conhecimento específico**.

A pergunta verifica **o conhecimento apresentado**.

Exemplo:

`Jornada → Montando um PC`

`Placa-mãe → função + fabricantes + sockets + compatibilidade`

`Processador → CPU + Intel/AMD + gerações + socket`

`Memória RAM → função + capacidade + DDR4/DDR5`

Dessa forma, a especificidade técnica fica nos artefatos, sem tornar a jornada dependente de uma configuração específica de computador.

### Controle de tamanho do repositório

O limite total é **1 GB**, portanto cada arquivo deve ser tratado como recurso limitado. Antes de adicionar um modelo ou imagem, verificar:

`resolução → formato → tamanho → necessidade real`

Não basta o arquivo funcionar. Ele também precisa ser **otimizado para a experiência e para o armazenamento do projeto**.
