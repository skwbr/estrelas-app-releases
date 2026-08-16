# Estrelas App — releases

Distribuição do APK do **Estrelas App**, o aplicativo de trabalho da equipe da
Estrelas Refrigeração (Parauapebas-PA).

Este repositório é **público de propósito e guarda apenas o instalador**: o
aparelho precisa baixar o APK sem credencial nenhuma, e o app se atualiza
sozinho a partir daqui. O código-fonte é privado e não está aqui.

## Instalar / atualizar

**Link direto (sempre a versão mais recente):**

```
https://github.com/skwbr/estrelas-app-releases/releases/latest/download/estrelas-app.apk
```

Normalmente você não precisa deste link: o próprio app avisa quando há versão
nova, baixa e instala. Ele serve para o primeiro install de um aparelho.

No Android, será preciso autorizar a instalação de fonte desconhecida uma única
vez — é o normal para app distribuído fora da Play Store.

## `latest.json`

O app consulta este arquivo para saber se está desatualizado:

| campo | para quê |
|---|---|
| `versionCode` | número que decide se há atualização (comparação de inteiro, não de texto) |
| `versionName` | o que aparece para a pessoa ("1.2.1") |
| `apkUrl` | de onde baixar |
| `sha256` | conferido depois do download, antes de instalar |
| `sizeBytes` | tamanho, para mostrar progresso |
| `notes` | o que mudou, em uma linha |

## Segurança

O APK é assinado com a chave de release da Estrelas. O Android **recusa**
instalar por cima uma atualização assinada com outra chave — então um arquivo
adulterado não substitui o app instalado. O app ainda confere o `sha256` antes
de chamar o instalador.
