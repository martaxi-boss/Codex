# Codex — instalacao independente na VPS Ubuntu

**Repositorio:** `martaxi-boss/Codex`. A presente arvore GitHub e um registo inicial da instalacao existente; **a publicacao integral do codigo/manifestos e a reproducibilidade ainda nao estao certificadas**.

## Pasta principal fisica

`/srv/projects/Codex` — diretorio fisico que contem o pacote existente `package.json`, `package-lock.json` e `node_modules/`. A antiga localizacao `/home/ubuntu/codex-agent` permanece apenas como ligacao de compatibilidade.

A pasta de integracao anteriormente em `/home/ubuntu/codex-bridge` foi **arquivada**, sem executar nem instalar um coordenador, em `/srv/projects/Codex/archive/legacy-bridge`. A origem antiga ficou temporariamente ligada ao arquivo. Nao confundir o Codex CLI com o coordenador do projeto `Project-leader-codex`, que pertence ao ambiente ChatGPT/Codex e nao deve ser colocado na VPS.

**Provas reais (04-11-2026):**
- [Actions #41751463892](https://github.com/martaxi-boss/VPS/actions/runs/41751463892) — primeiro isolamento fisico do pacote `codex-agent`.
- [Actions #41752751888](https://github.com/martaxi-boss/VPS/actions/runs/41752751888) — realocacao para raiz com nome identico ao repositorio e arquivo da integracao antiga; inodes, proprietarios e estados dos servicos preservados.

## Regras de independencia

- Codigo, dependencias privadas, configuracao e runtime deste projeto devem ficar dentro da raiz `/srv/projects/Codex`; nao utilizar instalacoes privadas de outros projetos.
- Nao publicar sessoes, chaves, credenciais, dados de jobs, dumps, cache ou arquivos de runtime no GitHub.
- Nao executar o arquivo `legacy-bridge` nem criar um coordenador residente na VPS.
- As ligacoes antigas apenas podem ser removidas apos actualizar consumidores, confirmar ausencia de referencias e testar reinicio.
- A desinstalacao isolada exige inventario de unit files, jobs/cron, caminhos externos e backup das configuracoes. **Ainda nao certificada apenas com remocao da pasta.**

O repo original estava vazio antes deste registo; **nao assumir que o GitHub reproduz toda a instalacao existente**. E preciso versionar manifestos limpos e um instalador auditado antes de afirmar alinhamento funcional completo.
