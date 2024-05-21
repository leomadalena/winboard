# Dashboard de Monitoramento do Windows com Grafana

## Descrição

Este dashboard foi criado para visualizar com o Grafana diversas métricas do sistema operacional Windows utilizando Prometheus e Windows Exporter. O objetivo principal é estudar e entender o monitoramento de sistemas Windows, incluindo o uso de CPU, memória RAM, espaço em disco e outras métricas relevantes.

## Pré-requisitos

- Windows Exporter instalado e configurado no sistema Windows.
- Prometheus configurado para coletar métricas do Windows Exporter.
- Grafana configurado para utilizar o Prometheus como fonte de dados.

## Instalação

### 1. Instalar o Windows Exporter

Baixe e instale o Windows Exporter a partir do [GitHub](https://github.com/prometheus-community/windows_exporter/releases).

### 2. Configurar o Prometheus

Adicione a seguinte configuração no arquivo `prometheus.yml` para coletar métricas do Windows Exporter:

```yaml
scrape_configs:
  - job_name: 'windows'
    static_configs:
      - targets: ['<WINDOWS_HOST>:9182']
