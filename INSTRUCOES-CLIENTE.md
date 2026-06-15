# ⚡ Configuração de Acesso Samax — Somente Leitura (Azure)

Para liberar o diagnóstico de **custos**, **inventário de recursos** e **métricas de consumo**, siga os 2 passos abaixo. Todo o acesso é **estritamente de leitura** — nenhuma permissão de alteração, exclusão ou de visualização do conteúdo de arquivos é concedida.

---

## Passo 1 — Criar o usuário de consultoria

1. Acesse o portal: **https://portal.azure.com**
2. Vá em **Microsoft Entra ID** → **Usuários** → **+ Novo usuário** → **Convidar usuário externo**.
3. Preencha o e-mail do consultor:
   - `consultor@samax.io`  *(ou `lucio@samax.io`, conforme combinado)*
4. Clique em **Convidar**.
5. Após criado, abra o usuário na lista e **copie o `Object ID`** (UUID que aparece no perfil). Você vai usá-lo no Passo 2.

> O consultor receberá um e-mail de convite e precisa **aceitá-lo** antes do primeiro acesso.

---

## Passo 2 — Aplicar o acesso (read-only)

1. Clique no link de implantação:

   👉 **[COLAR AQUI O LINK "Deploy to Azure"]**

2. Selecione a **Subscription** que será diagnosticada.
3. Em **Resource group**, selecione qualquer um existente (a atribuição é feita no nível da subscription; o RG é apenas exigência da tela).
4. No campo **Consultant Object Id**, cole o `Object ID` copiado no Passo 1.
5. Clique em **Revisar + criar** → **Criar**.

Pronto! O acesso é concedido em segundos.

---

## O que este acesso permite (e o que NÃO permite)

| Permite (somente leitura) | NÃO permite |
|---|---|
| Visualização total de custos, budgets e previsões | Criar, editar ou excluir qualquer recurso |
| Inventário de todos os recursos da subscription | Ver o **conteúdo** de arquivos em Storage |
| Configuração de Storage: tiers (hot/cool/archive), políticas de ciclo de vida e retenção | Ler dados de bancos, Key Vault ou aplicações |
| Métricas de consumo e utilização dos ambientes | Qualquer ação de escrita, configuração ou deleção |

**Roles aplicadas (todas built-in da Microsoft):** Reader · Cost Management Reader · Monitoring Reader.

---

## Pré-requisitos de quem executa

- **Passo 1:** perfil com permissão para convidar usuários (ex.: *User Administrator* / *Guest Inviter*).
- **Passo 2:** ser *Owner* ou *User Access Administrator* na subscription.

Dúvidas na execução? Entre em contato — acompanhamos o processo com você.
