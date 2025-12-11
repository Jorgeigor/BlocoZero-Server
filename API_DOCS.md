# EMPRESA

**EMPRESA**  
**Criar Empresa (Enterprise):**

- [http://localhost:8080/enterprise/register](http://localhost:8080/enterprise/register) Method:”POST”

	{  
  "name": "BlocoZero Construtora e Incorporadora",  
  "cnpj": "12753161000135",  
  "address": "Asa SUl",  
  "phone": "55679812312",  
  "email": "blocozero@gmail.com"  
}

**Listar Empresas:**

- [http://localhost:8080/enterprise/](http://localhost:8080/enterprise/register)list Method:”GET”

# USUÁRIOS

**USUÁRIOS**  
**Criar usuários:**

- [http://localhost:8080/user/register](http://localhost:8080/user/register) Method:”POST”

{  
  "enterprise\_id":1,  
  "userFunction":"manager", (função do usuário, pode ser tender ou manager)  
  "email":"joaomarreta@blocozero.com",  
  "password":"123456",  
  "phone":"55619999",  
  "works":"aaaaa",  
  "hourlyRate":120.00,  
  "name":"João Marreta Pinto Rego"  
}

**Listar usuários:**

- [http://localhost:8080/user/](http://localhost:8080/user/register)list/{enterprise\_id} Method:”GET”

**Listar usuário específico:**

- [http://localhost:8080/user/](http://localhost:8080/user/register)specific/{id\_user} Method:”GET”

**Fazer login:**

- [http://localhost:8080/user/](http://localhost:8080/user/register)login Method:”POST”

{  
  "email":"joaomarreta@blocozero.com",  
  "password":"123456"  
}

**Atualizar usuário:**

- [http://localhost:8080/user/](http://localhost:8080/user/register)update/{id\_user} Method: “PUT”

{  
  "enterprise\_id": 1, (enterprise id que o usuário está relacionado)  
  "userFunction": "manager",  
  "email": "joaomarreta@blocozero.com",  
  "password": "123456",  
  "phone": "55619999",  
  "works": "aaaaa",  
  "hourlyRate": 300.00,  
  "name": "João Marreta Pinto Rego"  
}

**Deletar usuário: (Somente desativa)**

- [http://localhost:8080/user/](http://localhost:8080/user/register)delete/{id\_user} Method:”DELETE”

# OBRAS

**OBRAS**  
**Criar obra:**

- [http://localhost:8080/work/register](http://localhost:8080/work/register)  \-\> Method:”POST”a

**Form-data:**

* id\_entreprise: 1  
* id\_manager:1  
* title:Construção hospital UCB  
* cnpj:702555000120  
* address:Ceilândia  
* cep:72555654  
* budget:100000000  
* start\_time:2025-10-21 00:00:00  
* end\_time:2026-10-21 00:00:00  
* description:Construção do hospital da UCB formando  
* photo: (AQUI TEM QUE SER ENVIADO O ARQUIVO)  
* tender\_id::2

**Pegar foto da obra pelo seu id:**

- http://localhost:8080/work/photo/{id\_work}

**Listar obras (retorna as 5 primeiras):**

- [http://localhost:8080/work/list/{enterprise\_id](http://localhost:8080/work/list/{enterprise_id)} Method:”GET”

**Listar obras por página:**

- [http://localhost:8080/work/list/{enterprise\_id}/page/{page](http://localhost:8080/work/list/{enterprise_id}/page/{page) number} Method:”GET”

**Listar obra específica:**

- [http://localhost:8080/work/specific/{id\_work](http://localhost:8080/work/specific/{id_work)}

**Atualizar obra específica:**

- [http://localhost:8080/work/update/{id\_work](http://localhost:8080/work/update/{id_work)} Method:”PUT”

**Form-data:**

* id\_entreprise: 1  
* id\_manager:1  
* title:Construção hospital UCB  
* cnpj:702555000120  
* address:Ceilândia  
* cep:72555654  
* budget:100000000  
* start\_time:2025-10-21 21:00:00  
* end\_time:2026-10-21 22:00:00  
* describe:Construção do hospital da UCB formando  
* photo: (AQUI TEM QUE SER ENVIADO O ARQUIVO)  
* id\_tender:2

**Deletar (desativar):**

- [http://localhost:8080/work/delete/{id\_work](http://localhost:8080/work/delete/{id_work)} Method:”DELETE”

# ORÇAMENTO

**ORÇAMENTO**  
**Criar orçamento (mão de obra):**

- [http://localhost:8080/budget/registerLabor](http://localhost:8080/budget/registerLabor) \- Method: “POST”

 {  
  "id\_work": 1,  
  "employee\_id": 2,  
  "hours\_worked": 10,  
  "allocated\_stage\_id": 1,  
  "id\_type": 2,  
  "id\_category": 1,  
  "function": "Gerenciar progresso da obra"  
}

**Listar orçamentos:**

- [http://localhost:8080/budget/list](http://localhost:8080/budget/list)/{work\_id} Method:”GET”

- 

# TIPO

**TIPO**  
**Criar type:**

- [http://localhost:8080/type/register](http://localhost:8080/type/register) Method:”POST”

{  
  "name": "Material",  
   “work\_id”:1  
}

**Listar types:**

- [http://localhost:8080/type/list](http://localhost:8080/type/list)/{id\_work}  
- Method:”GET”

**Update Types:**

- [http://localhost:8080/type/update/{id\_type](http://localhost:8080/type/update/{id_type)} Method:”PUT”

{  
  "name": "Material",  
   “work\_id”:1  
}

**Deletar type:**

- [http://localhost:8080/type/delete/{id\_type](http://localhost:8080/type/delete/{id_type)}  Method:”DELETE”

**A FUNÇÃO DELETE TYPE RETIRA PRATICAMENTE TUDO DO SISTEMA (FK DE MUITA COISA), ENTÃO É BOM COLOCAR UM AVISO (ALERT) PARA O USUÁRIO QUANDO ELE FOR APAGAR ALGUM TYPE(TIPO).**

# CATEGORIA

**CATEGORIA**  
**Criar categoria:**

- [http://localhost:8080/category/register](http://localhost:8080/category/register) Method:”POST”   
  {  
    "name": "Material de obra",  
    “id\_type”: 1  
  }


  
**Listar categorias:**

- [http://localhost:8080/category/list](http://localhost:8080/category/list)/{work\_id}   
- Method:”GET”  
  


  
**Atualizar categorias:**

- [http://localhost:8080/category/update/{id\_category](http://localhost:8080/category/update/{id_category)} Method:”PUT”

{  
  "name": "Materiais em geral",  
  "id\_type": 3  
}

**Excluir categoria:**

- [http://localhost:8080/category/delete/{id\_category](http://localhost:8080/category/delete/{id_category)}  
- Method:”PUT”


**A FUNÇÃO DELETE CATEGORY RETIRA PRATICAMENTE TUDO DO SISTEMA (FK DE MUITA COISA), ENTÃO É BOM COLOCAR UM AVISO (ALERT) PARA O USUÁRIO QUANDO ELE FOR APAGAR ALGUM CATEGORY(CATEGORIA).**

# ESTOQUE

# Estoque

**Criar item no estoque**   
Method: POST  
http://localhost:8080/stock/create  
{  
  "id\_type": 1,  
  "id\_category": 1,  
  "id\_work": 1,  
  "code": "MAT-002",  
  "name": "Areia Média",  
  "unitMeasure": "M³",  
  "stockQuantity": 75,  
  "weightLength": 30,  
  "minQuantity": 15,  
  "costUnit": 120.00  
}

**Listar itens disponíveis no estoque pelo id da obra:**  
Method: Get  
[http://localhost:8080/stock/{work\_id](http://localhost:8080/stock/{work_id)}

**Informar retirada de algum item do stock:**  
Method: Post  
[http://localhost:8080/stock/exit](http://localhost:8080/stock/exit)  
{  
  "employee\_id":1,  
  "id\_item":2,  
  "quantity":20  
}

**Informar entrada de algum item do stock:**  
Method: Post  
[http://localhost:8080/stock/](http://localhost:8080/stock/exit)entry  
{  
  "employee\_id":1,  
  "id\_item":2,  
  "quantity":2000  
}

FALTA IMPLEMENTAR UPDATE E DELETE   
	

# ETAPA

**ETAPA**

**Criar Etapa:**  
[http://localhost:8080/stage/register](http://localhost:8080/stage/register)  
Method: POST  
{  
  "name": "Fundação",  
  "progress": 0,  
  "expStartDate": "2025-10-21",  
  "expEndDate": "2025-12-01",  
  "exeStartDate": "",  
  "exeEndDate": "",  
  "id\_work": 1  
}

**List all**:  
[http://localhost:8080/stage/list/{work\_id](http://localhost:8080/stage/list/{work_id)}  
Method: GET

**Update**  
[http://localhost:8080/stage/update/](http://localhost:8080/stage/update/4){id\_stage}  
Method:PUT

{  
  "name": "Fundação",  
  "progress": 0,  
  "expStartDate": "2025-10-21",  
  "expEndDate": "2025-12-01",  
  "exeStartDate": "",  
  "exeEndDate": ""  
}

**Delete**  
[http://localhost:8080/stage/delete/4](http://localhost:8080/stage/delete/4)  
Method: DELETE

# SUB-ETAPA

**Registrar Subtapa**  
[http://localhost:8080/substage/register](http://localhost:8080/substage/register)  
Method:Post  
{  
  "stage\_id":1,  
  "name": "escavação",  
  "expDuration": "2025-10-21",  
  "progress": 25,  
  "employees": \[  
    {  
      "user\_id": 1,  
      "hours\_worked": 10,  
      "userfunction": "Gerenciar"  
    },  
    {  
      "user\_id": 2,  
      "hours\_worked": 15,  
      "userfunction": "Operações em geral"  
    },  
    {  
      "user\_id": 3,  
      "hours\_worked": 6,  
      "userfunction": "Planejamento e acompanhamento de etapas"  
    }  
  \],  
  "items\_usage": \[  
    {  
      "item\_id": 1,  
      "quantity\_usage": 15  
    },  
    {  
      "item\_id": 4,  
      "quantity\_usage": 20  
    },  
    {  
      "item\_id": 11,  
      "quantity\_usage": 200  
    }  
  \]  
}

**Listar todas as subetapas:**

- [http://localhost:8080/substage/list/{work\_id](http://localhost:8080/substage/list/{work_id)}  
- Method:”GET”

**Atualizar uma Subetapa**

- [http://localhost:8080/substage/update/{id\_subetapa](http://localhost:8080/substage/list/{work_id)}  
- {   
- "name": "Escavação EDITADO )",   
- "expDuration": "2025-12-30",  
-  "progress": 50   
- }  
- Method: “PUT”


**Deletar uma subetapa**

- [http://localhost:8080/substage/delete/{id\_subetapa](http://localhost:8080/substage/list/{work_id)}  
- Method : “DELETE”

# CRONOGRAMA

**Listar Cronograma Físico** 

- [http://localhost:8080/physicalSchedule/list/](http://localhost:8080/stage/delete/4){id\_work}

Method: “GET”

Create,update e delete do cronograma é junto com a rota de register de subetapa

# Fisico-Financeiro

**Obter Relatório Físico-Financeiro da Obra**

- http://localhost:8080/financialphysical/list/{workId}

**Method: GET**

# ProgressReport

**RELATÓRIOS DE PROGRESSO**

**Criar relatório:**

[http://localhost:8080/progress-report/register](http://localhost:8080/progress-report/register)

 \-\> Method: POST

{

Form-data:  
id\_work: 1  
id\_employee: 5  
title: Relatório de Fundação  
description: Finalizada a concretagem das sapatas da ala norte.  
date\_reference: 2025-12-05  
percentage\_completed: 10  
photo: (AQUI TEM QUE SER ENVIADO O ARQUIVO)

}

**Listar relatórios por obra** (Pelo ID da Obra):

[http://localhost:8080/progress-report/list/{id\_work}](http://localhost:8080/progress-report/list/%7Bid_work%7D)

 \-\> Method: GET

**Atualizar relatório (Funcionário):**

[http://localhost:8080/progress-report/update/{id\_report}](http://localhost:8080/progress-report/update/%7Bid_report%7D)

 \-\> Method: PUT

{

Form-data:  
description: Correção: Finalizada a concretagem e iniciada a cura do concreto.  
photo: (AQUI TEM QUE SER ENVIADO O ARQUIVO)  
date\_reference: 2025-12-05  
percentage\_completed: 12

}

**Revisar relatório (Gerente):**

[http://localhost:8080/progress-report/review/{id\_report}](http://localhost:8080/progress-report/review/%7Bid_report%7D)

 \-\> Method: PATCH

{

Form-data:  
id\_manager: 2  
status: APROVADO  
feedback: Bom andamento, fotos conferem com o cronograma.  
approved\_at: 2025-12-06 10:00:00

}

