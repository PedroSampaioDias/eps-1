
# Relatório de Prontidão Técnica: Onboarding SecOps

**Disciplina:** Engenharia de Produto de Software (FGA0316) - 2026.1  
**Aluno:** Pedro Sampaio Dias Rocha | **Matrícula:** 21/1043745  

## 1. Configuração do Ambiente (Zero Trust & Isolamento)  
Conforme as diretrizes de Soberania Técnica, as seguintes configurações foram aplicadas:  
- [x] **Python 3.12:** Instalado e verificado.  
- [x] **Poetry:** Configurado para criar `.venv` dentro do projeto (`virtualenvs.in-project true`).  
- [x] **Determinismo:** Arquivos `pyproject.toml` e `poetry.lock` gerados com sucesso.

## 2. Logs de Auditoria e Qualidade (Security Gate)

### 2.1. Auditoria Estática (Bandit)

```
pedro@sampas:~/eps/pcdf$ poetry run bandit -r .
[main]  INFO    profile include tests: None
[main]  INFO    profile exclude tests: None
[main]  INFO    cli include tests: None
[main]  INFO    cli exclude tests: None
[main]  INFO    running on Python 3.12.0
Run started:2026-03-29 20:51:04.904114+00:00

Test results:
        No issues identified.

Code scanned:
        Total lines of code: 4
        Total lines skipped (#nosec): 0

Run metrics:
        Total issues (by severity):
                Undefined: 0
                Low: 0
                Medium: 0
                High: 0
        Total issues (by confidence):
                Undefined: 0
                Low: 0
                Medium: 0
                High: 0
Files skipped (0):
```

### 2.2. Verificação de Dependências (Safety)

```
pedro@sampas:~/eps/pcdf$ poetry run safety check


+===========================================================================================================================================================================================+


DEPRECATED: this command (`check`) has been DEPRECATED, and will be unsupported beyond 01 June 2024.


We highly encourage switching to the new `scan` command which is easier to use, more powerful, and can be set up to mimic the deprecated command if required.


+===========================================================================================================================================================================================+


+====================================================================================+

                               /$$$$$$            /$$
                              /$$__  $$          | $$
           /$$$$$$$  /$$$$$$ | $$  \__//$$$$$$  /$$$$$$   /$$   /$$
          /$$_____/ |____  $$| $$$$   /$$__  $$|_  $$_/  | $$  | $$
         |  $$$$$$   /$$$$$$$| $$_/  | $$$$$$$$  | $$    | $$  | $$
          \____  $$ /$$__  $$| $$    | $$_____/  | $$ /$$| $$  | $$
          /$$$$$$$/|  $$$$$$$| $$    |  $$$$$$$  |  $$$$/|  $$$$$$$
         |_______/  \_______/|__/     \_______/   \___/   \____  $$
                                                          /$$  | $$
                                                         |  $$$$$$/
  by safetycli.com                                        \______/

+====================================================================================+

 REPORT 

  Safety v3.7.0 is scanning for Vulnerabilities...
  Scanning dependencies in your environment:

  -> /opt/ros/humble/lib/python3.10/site-packages
  -> /opt/ros/humble/local/lib/python3.10/dist-packages
  -> /home/pedro/eps/.venv/lib/python3.12/site-packages

  Using open-source vulnerability database
  Found and scanned 197 packages
  Timestamp 2026-03-29 17:55:04
  0 vulnerabilities reported
  0 vulnerabilities ignored
+====================================================================================+

 No known security vulnerabilities reported. 

+====================================================================================+


+===========================================================================================================================================================================================+


DEPRECATED: this command (`check`) has been DEPRECATED, and will be unsupported beyond 01 June 2024.


We highly encourage switching to the new `scan` command which is easier to use, more powerful, and can be set up to mimic the deprecated command if required.


+===========================================================================================================================================================================================+
```

### 2.3. Qualidade e Conformidade (Ruff)

```
pedro@sampas:~/eps/pcdf$ poetry run ruff check .
All checks passed!
```

## 3. Evidência de Integração Contínua (CI)

- **Link da Action de Sucesso:** https://github.com/PedroSampaioDias/eps-1/actions/runs/23719284416/job/69091472787

## 4. Declaração de Prontidão

Declaro que o ambiente de desenvolvimento foi configurado com sucesso utilizando Python 3.12 e Poetry, conforme as diretrizes estabelecidas.

As ferramentas de segurança (Bandit, Ruff e Safety) foram executadas e não apresentaram vulnerabilidades ou inconsistências no código inicial.

O repositório foi devidamente versionado e integrado ao GitHub, com pipeline de Integração Contínua (CI) configurado e validado com sucesso.

Dessa forma, confirmo que o código está apto para migração via Git Remote para a organização oficial da disciplina.

## 5. Declaração de Soberania Técnica (CISSP Domain 8)

Eu, Pedro Sampaio Dias Rocha, declaro que auditei manualmente as ferramentas e dependências deste projeto. Confirmo que o código gerado via IA passou pela minha revisão humana, garantindo que não há falhas críticas.

**Data de Entrega:** 30/03/2026  

## Observações

Ambiente configurado com sucesso. Recomenda-se futuramente migrar para `safety scan`.
