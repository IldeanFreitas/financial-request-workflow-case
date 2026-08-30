# Cenários de teste

| ID | Cenário | Resultado esperado |
| --- | --- | --- |
| FT-01 | Criar rascunho com campos mínimos | Registro permanece em `draft` e pode ser continuado |
| FT-02 | Enviar solicitação com rateios que somam o total | Estado muda para `submitted` e a chave de idempotência é preservada |
| FT-03 | Tentar enviar com soma de rateios divergente | Envio é bloqueado com mensagem de validação |
| FT-04 | Reenviar a mesma chave de idempotência | O destino recebe no máximo uma solicitação lógica |
| FT-05 | Retorno positivo do processamento externo | Estado avança para `approved` sem alterar os valores enviados |
| FT-06 | Retorno negativo do processamento externo | Estado muda para `rejected` com motivo de negócio registrável |
| FT-07 | Confirmar liquidação após aprovação | Estado final muda para `paid` e histórico é mantido |
| FT-08 | Cancelar antes do processamento | Estado muda para `cancelled`; não ocorre exclusão física |
| FT-09 | Anexar evidência | Apenas metadados permitidos são associados; arquivo fica fora do contrato público |
| FT-10 | Falha temporária do adaptador | Automação registra falha recuperável e não apresenta sucesso prematuro |
