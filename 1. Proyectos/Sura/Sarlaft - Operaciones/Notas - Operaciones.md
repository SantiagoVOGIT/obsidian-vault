
**6587720**:
- C16485136
- Evaluaciones:
	- 7955ef02-75ae-4ba7-b1d7-4b7f82000cd2 **(BUGEADA)**
		- **Fecha de creación:** `8:43 A.M / 26 SEP`
		- 

	- 471b0df7-12d7-4c07-b5f9-256d7bc9fe09 **(CORRECTA)**
		- **Fecha de creación:** `10:18 A.M / 26 SEP
		- 



request: {"tipoDocumento":"CE","numeroDocumento":"333560","primerApellido":"SHAFI"}
response: {"codigoRespuesta":"09","descripcionRespuesta":"NO existe este número de identificación en los archivos de validación de la base de datos.","fechaConsulta":"Sep 7, 2024, 4:50:28 AM"}


Cordial saludo,

Se verifica que en el historial de logs relacionados con el proceso en cuestión de validación de identidad se identifica que se esta llamando a este servicio REST (JSON) para realizar la validación: ``
`https://servicesesb.datacredito.com.co:444/da/migracion/v1/persona`, 
este es el request:

```
{"tipoDocumento":"CE","numeroDocumento":"333560","primerApellido":"SHAFI"}
```

este es el response: 

```
{"codigoRespuesta":"09","descripcionRespuesta":"NO existe este número de identificación en los archivos de validación de la base de datos.","fechaConsulta":"Sep 7, 2024, 4:50:28 AM"}
```


Mi hermano, usted es una persona que tiene mucho potencial y sabiduría, se sabe expresar muy bien y suele dar un buen análisis de las cosas. Aprovecha esa capacidad que tienes, pero también intenta escuchar los consejos de los otros, y aún así sean negativos sacarles el lado positivo


**Bases de datos (PDN):**
- Transaccional (core): `psql-srsarlaftp7fca05e4`
- No transaccional: (backup, administrativo): `psql-srsarlaftpba1b6649`

index="idx_sarlaft4_err" "modulo=FUNCTION-WEBHOOK" "*WebhookRestAdapterRest.notificationPost*"


```
SELECT *  
FROM sarlaft.tsaf_evaluacion  
WHERE nmevaluacion = '{idEvaluacion}'
```


{
    "solicitudDni": "C0000001",
    "codigoOperacion": "01",
    "codigoAplicacion": "6919",
    "negocioId": "01",
    "infoPendiente": false,
    "tomador": {
        "personaPep": "si",
        "administradorPep": null,
        "cliente": {
            "tipoPersona": "N",
            "correo": "chernandezm@sura.com.co",
            "celular": "3043515225",
            "razonSocial": null,
            "paisConstitucion": null,
            "documento": {
                "tipo": "C",
                "numero": "1085962306",
                "fechaExpedicion": "1988-06-14"
            },
            "persona": {
                "primerNombre": "LILIA",
                "segundoNombre": null,
                "primerApellido": "AMPARO",
                "segundoApellido": "BERNAL",
                "pais": "57"
            }
        }
    },
    "polizas": [
        {
            "codigoRamo": "012",
            "codigoProducto": "%",
            "codigoCanal": "CC016",
            "valorAsegurado": 7800000000,
            "valorPrima": 200000,
            "medioPago": null,
            "negocio": "INDIVIDUAL",
            "tipoCoaseguro": null,
            "codigoOficina": "00",
            "codigoAgente": "00"
        }
    ]
}


