$ IsiTable
Sistema de geração de tabelas sob demanda via API SpringBoot
Por que este projeto?

Para que consigamos ter uma API que funcione parecido com um "AirTable", ou seja, o Usuário pode criar uma (ou mais) estruturas de tabelas e preencher dados nela via API REST (teremos um Backend que consiga manipular as operações básicas de GET/POST/PUT/DELETE em cada registro das tabelas)

Uma idéia de modelagem é a exibida a seguir:
```mermaid
erDiagram
    USER ||..|{ PROJECT: has
    PROJECT ||..|{ TABLE: has

    
```


Estrutura do JSON armazenado

```json
{	
  "tableId":1,
  "metadata":[
		{
          "fieldId": 1,		
		  "fieldName":"id_lead",
		  "fieldType":"autonumber"
	    },
		{
          "fieldId": 2,		
		  "fieldName":"nome",
		  "fieldType":"single_line"
	    },
		{
          "fieldId": 3,		
		  "fieldName":"email",
		  "fieldType":"email"
	    },
		{
          "fieldId": 4,		
		  "fieldName":"telefone",
		  "fieldType":"phone_number"
	    }
	],
	"data":[
		{
			"row": [
				{
					"fieldName":"id_lead",
					"value": "1"	
				},
				{
					"fieldName":"nome",
					"value": "Professor Isidro"
				},
				{
					"fieldName":"email",
					"value": "isidro@isidro.com"
				},
				{
					"fieldName":"telefone",
					"value": "11987654321"
				}
			]
		},
	    {
			"row" : [
				{
					"fieldName":"id_lead",
					"value": "2"	
				},
				{
					"fieldName":"nome",
					"value": "Joao do Teste"
				},
				{
					"fieldName":"email",
					"value": "joao@teste.com"
				},
				{
					"fieldName":"telefone",
					"value": "11987654322"
				}
			
			]				
		}
	]	
}
```
