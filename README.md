# Para cada objetivo será criado uma pasta, para manter a organização de cada script
<img src="https://github.com/tbarcelar/python/blob/main/logo.JPG" width="1200" height="300">

Se quiser fazer uma api testando um emulador de servidor instale UVICORN, para testar a conexão segue o script. O nome do arquivo é teste_api

import uvicorn
async def app(scope, receive, send):
    assert scope['type'] == 'http'
    await send({
        'type': 'http.response.start',
        'status': 200,
        'headers': [
            [b'content-type', b'text/plain'],
        ],
    })
    await send({
        'type': 'http.response.body',
        'body': b'Seu api funcioando aeeeeeeeeeee!',
    })
    uvicorn.run("teste_api:app", host="127.0.0.1", port=5000, log_level="info")

