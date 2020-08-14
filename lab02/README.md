
## Tarefa sobre catálogo de componentes
[Notebook](notebook/components-01-catalog.ipynb)

## Tarefa Web Components 1
```sh
<dcc-trigger label="Mundo" action="noticia/mundo/politica" value="mundo politica"></dcc-trigger>
<dcc-trigger label="Brasil P" action="noticia/brasil/politica" value="brasil politica"/></dcc-trigger>
<dcc-trigger label="Brasil E" action="noticia/brasil/esporte" value="brasil esporte"/></dcc-trigger>
<dcc-trigger label="Bahia" action="noticia/Bahia/esporte" value="bahia esporte"/></dcc-trigger>

<dcc-lively-talk delay="delay" character="doctor" speech="Eu gosto de ler sobre ">
<subscribe-dcc topic="noticia/#/politica"/>
</dcc-lively-talk>

<dcc-lively-talk delay="delay" character="nurse" speech="Eu gosto de ler sobre ">
<subscribe-dcc topic="noticia/brasil/#"/>
</dcc-lively-talk>

<dcc-lively-talk delay="delay" character="patient" speech="Eu gosto de ler sobre ">
<subscribe-dcc topic="noticia/#"/>
</dcc-lively-talk>
```

## Tarefa Web Components 2
```sh
<dcc-trigger label="News" action="next/rss">
</dcc-trigger>

<dcc-rss source="https://www.wired.com/category/science/feed" publish="rss/science">
  <subscribe-dcc topic="next/rss" role="step"></subscribe-dcc>
</dcc-rss>

<dcc-rss source="https://www.wired.com/category/design/feed" publish="rss/design">
  <subscribe-dcc topic="next/rss" role="step"></subscribe-dcc>
</dcc-rss>

<dcc-aggregator publish="aggregate/science" quantity="3">
  <subscribe-dcc topic="rss/science"></subscribe-dcc>
</dcc-aggregator>

<dcc-lively-talk id="doctor"
                 duration="0s"
                 character="doctor">
  <subscribe-dcc topic="aggregate/science"></subscribe-dcc>
</dcc-lively-talk>

<dcc-lively-talk id="nurse"
                 duration="0s"
                 character="nurse">
  <subscribe-dcc topic="rss/science"></subscribe-dcc>
</dcc-lively-talk>

<dcc-lively-talk id="doctor"
                 duration="0s"
                 character="patient">
  <subscribe-dcc topic="rss/design"></subscribe-dcc>
</dcc-lively-talk>
```
