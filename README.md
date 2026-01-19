# Projeto Trilhas

Aplicativo Android nativo desenvolvido em Java para registro, monitoramento e gerenciamento de trilhas e caminhadas ao ar livre. O projeto utiliza a API do Google Maps e serviços de localização para traçar rotas em tempo real e calcular estatísticas de desempenho.

Este aplicativo foi desenvolvido como parte de um trabalho acadêmico (Engenharia de Software/Sistemas de Informação).

## Funcionalidades

* **Rastreamento em Tempo Real:** Monitoramento da localização do usuário via GPS (`FusedLocationProviderClient`) com desenho da rota no mapa enquanto a atividade acontece.
* **Estatísticas de Desempenho:** Cálculo dinâmico de distância percorrida, velocidade atual, velocidade máxima e estimativa de calorias queimadas (baseada no peso do usuário configurado).
* **Histórico Local:** Persistência dos dados das trilhas utilizando banco de dados interno (SQLite).
* **Visualização de Detalhes:** Consulta de trilhas anteriores com mapa estático da rota e resumo dos dados.
* **Exportação de Dados:** Funcionalidade para exportar os dados da trilha para formatos padrão de mercado:
* JSON
* CSV
* KML (Google Earth)
* GPX (GPS Exchange Format)


* **Configurações:** Personalização de dados do usuário (peso/altura para cálculos) e estilo do mapa (Vetorial/Satélite).

## Tecnologias Utilizadas

* **Linguagem:** Java
* **SDK:** Android SDK (Min API 24)
* **Mapas:** Google Maps SDK for Android
* **Localização:** Google Play Services Location
* **Banco de Dados:** SQLite (via `SQLiteOpenHelper`)
* **IDE:** Android Studio

## Configuração e Instalação

Para rodar o projeto localmente, você precisará do Android Studio instalado.

1. **Clonar o repositório:**
```bash
git clone https://github.com/seu-usuario/projeto-trilhas.git

```


2. **Configurar a API Key do Google Maps:**
O projeto depende do Google Maps para funcionar corretamente. Você precisa gerar uma chave de API no Google Cloud Console com as seguintes APIs ativadas:
* Maps SDK for Android
* Places API (opcional, se utilizado)


No arquivo `AndroidManifest.xml`, localize a tag `meta-data` e insira sua chave:
```xml
<meta-data
    android:name="com.google.android.geo.API_KEY"
    android:value="SUA_CHAVE_AQUI" />

```


3. **Compilar e Rodar:**
Abra o projeto no Android Studio, aguarde o sync do Gradle e execute em um emulador ou dispositivo físico.
> **Nota:** Para testar o rastreamento GPS no emulador, é necessário enviar coordenadas de localização simuladas através das ferramentas do emulador (Extended Controls > Location).



## Estrutura do Projeto

O código segue a estrutura padrão de Activities do Android:

* `RegistrarTrilhaActivity`: Lógica de captura de GPS e serviço de localização.
* `ConsultarTrilhasActivity`: Listagem do histórico (RecyclerView).
* `DetalhesTrilhaActivity`: Visualização pós-trilha e lógica de exportação de arquivos.
* `TrilhasDBHelper` / `TrilhasDAO`: Camada de persistência de dados.

## Licença

Este projeto é de cunho educacional. Sinta-se à vontade para estudar o código ou utilizá-lo como base para estudos.
