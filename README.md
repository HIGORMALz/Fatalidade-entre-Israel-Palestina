# Fatalidades Conflito entre Israel-Palestina 2000 a 2023
---

## Tópicos

<div>
 • <a href="#-sobre-o-projeto">Sobre o Projeto</a> </br>
 • <a href="#-tecnologias">Tecnologias</a> </br>
 • <a href="#-visualizacao-dos-dados">Visualização dos Dados</a> </br>
 • <a href="#-autor">Autor</a> </br>
</div>

 ## Sobre o Projeto.

Nesse projeto vamos analisar o perfil das vítimas com base nos dados disponíveis, como idade, sexo, cidadania e local de residência. com intuito de identificar características comuns entre as vitimas. Vamos analisar também os meios pelo qual os individuos foram mortos. Determinar as armas ou métodos mais usados e avaliar o impacto.

## Tecnologias 🚀

<div style="display: inline_block"><br/>
  <img align="center" alt="Python" src="https://img.shields.io/badge/Python-14354C?style=for-the-badge&logo=python&logoColor=white"/>
</div><br/>


## Visualização dos Dados.

### **Distribuição entre Sexo e Idade das vítimas**
```
fig, axes = plt.subplots(1, 2, figsize = (20, 6),dpi=200)
sns.boxplot(data=israel_palestine,x='sexo',y='idade',ax=axes[0]).set_title('Sexo vs Idade')
sns.countplot(data=israel_palestine,x='sexo',ax=axes[1],palette='icefire').set_title('Count plot For Sex')
plt.show()
```
![sexo-idade1](https://github.com/HIGORMALz/Fatalidade-entre-Israel-Palestina/assets/138539839/16fa4de1-2bea-45c9-8dc3-519be0444c90)

**Insights Extraidos**

O gráfico ilustra a distribuição por gênero e idade das vítimas:

* A maioria das vítimas fatais era do sexo masculino;
* Maioria das vítimas masculinas tinham entre 20 a 30 anos;
* A maioria das vítimas do sexo feminino se concentra entre 20 a 50 anos;

---


### **Relação entre idade e entidade responsável**

```
fig, axes = plt.subplots(1, 2, figsize = (20, 6),dpi=200)
sns.boxplot(data=israel_palestine,x='idade',y='morto_por',ax=axes[0]).set_title('Relação Entre idade e Entidade Responsável')
sns.countplot(data=israel_palestine,x='morto_por',ax=axes[1],palette='icefire')
plt.show()
```
![Relação Entre idade e Entidade Responsável (1)](https://github.com/HIGORMALz/Fatalidade-entre-Israel-Palestina/assets/138539839/9ff33709-f9be-4a85-987d-35602b582d3e)

**Insights Extraidos**

O gráfico exibe a distribuição das entidades responsáveis pelas fatalidades e se exite alguma correlação com a idade:

* Os incidentes fatais causado por civis palestinos tem a maior concentração em 20 a 50 anos, onde se encontra a maior parte de vítimas do sexo femininio;
* As forças de segurança israelenses são responsáveis por uma maioria significativa das mortes;
* Maior parte das vítimas mortas pelas forças de segurança israelenses tem entre 20 e 30 anos;
---

### **Visualizando o top 15 locais comuns de residência entre as vítimas**

```
residence_distribution = israel_palestine['local_de_residencia'].value_counts().head(15)

fig1 = px.bar(
    x=residence_distribution.index,
    y=residence_distribution.values,
    title='Top 15 locais comuns de residência entre as vítimas',
    labels={'x': 'Local de residência', 'y': 'Número de Fatalidades'},
    color=residence_distribution.index,
    color_discrete_sequence=px.colors.qualitative.Dark24,
)

fig1.update_layout(xaxis_tickangle=-40, xaxis_title='Local de residência', yaxis_title='Número de Fatalidades')
fig1.show()
```
![image](https://github.com/HIGORMALz/Fatalidade-entre-Israel-Palestina/assets/138539839/a3403911-cc5e-4418-a3bf-17b7f1a9dd03)

**Insights Extraidos**

O gráfico exibe os 15 locais mais comuns entre as vítimas:

* Gaza city disparadamente se destaca como o local de residência com o maior número de vítimas mortas;
* As três primeiras cidades do gráfico representam cidades da palestina;
* As regiões que contém grandes números de vítimas são cidades da palestina;

---

### **Visualizando os meios pelo qual os indivíduos foram mortos**

```
injury_distribution = israel_palestine['tipo_de_injuria'].value_counts()

injury_df = injury_distribution.reset_index()
injury_df.columns = ['Tipo de Injuria', 'Número de Fatalidades']

fig = px.bar(injury_df, x='Tipo de Injuria', y='Número de Fatalidades',
             title='Distribuição entre tipos de injuria',
             labels={'Número de Fatalidades': 'Número de Fatalidades'},
             color='Número de Fatalidades', color_continuous_scale='tropic')

fig.update_layout(xaxis_title='Tipo de Injuria', yaxis_title='Número de Fatalidades',
                  xaxis=dict(tickmode='array', tickangle=40), bargap=0.2)
fig.show()
```

![image2](https://github.com/HIGORMALz/Fatalidade-entre-Israel-Palestina/assets/138539839/a9e826db-5175-4ce9-9a58-6e5c7980b039)

**Insights Extraidos**

O gráfico apresenta diferentes tipos de injura:

* Armas são o maior responsável pelas mortes. Outros tipos de ferimentos, como os de explosões ou bombardeios, estão presentes, porém em números muito menores.

## Autor

Desenvolvido por **Higor Silva** 👋🏻

# Entre em contato

[![Linkedin](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/higor-silva-4a7341273/)









