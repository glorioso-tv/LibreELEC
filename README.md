As Imagens que estão aqui foi testada com a memoria eMMC então não sei se funciona em nand teste e ver mais sempre façam backup da rom ...

🛠️ Como gravar multitool.img no cartão SD ou pendrive (Linux)

Este tutorial mostra como gravar a imagem multitool.img em um cartão microSD ou pendrive para uso em TV Boxes compatíveis com LibreELEC.
⚠️ Aviso

Tenha certeza absoluta do dispositivo (ex: /dev/sdc) que você irá usar. O comando dd irá apagar tudo nele!
✅ Passo a passo
1. Baixe a imagem multitool

🔗 Clique aqui para baixar [multitool.img](https://github.com/glorioso-tv/LibreELEC/releases/download/LibreELEC/multitool.img)
 Descubra qual é seu dispositivo

Conecte o cartão SD ou pendrive e execute:

lsblk

Anote o caminho do dispositivo (ex: /dev/sdc). Não use partições como /dev/sdc1.

3. Grave a imagem no dispositivo


sudo dd if=multitool.img of=/dev/sdX bs=4M status=progress


Substitua /dev/sdX pelo nome correto do seu dispositivo, como /dev/sdc.
4. Garante que todos os dados sejam gravados

sync


Esse comando força a gravação de todos os dados em cache no dispositivo — evita corrupção.
5. Ejete o dispositivo com segurança

sudo eject /dev/sdc


📺 Usando o Multitool na TV Box

    Insira o cartão com Multitool na TV Box desligada.

    Conecte o cabo HDMI e a fonte de energia — a TV Box irá iniciar no Multitool.

    Faça um backup da NAND ou eMMC (memória interna) da TV Box.
    Use a opção no menu do Multitool: Backup NAND Flash ou similar.

    O backup será salvo automaticamente no cartão SD, na pasta backups/.

💾 Copiando a imagem do sistema para o cartão (no PC)

Depois do backup:

    Remova o cartão da TV Box e conecte novamente ao PC.

    Você verá uma partição chamada Multitool montada.

    Copie a imagem do sistema (por exemplo, LibreELEC) para a pasta images/.

Exemplo de imagem recomendada:

🔗 [LibreELEC](https://github.com/glorioso-tv/LibreELEC/releases/download/LibreELEC/LibreELEC-RK322X.arm-12.0-nightly-20250218-6a1e364-rk322x.img)
🧩 Instalando o sistema na TV Box

    Coloque o cartão de volta na TV Box.

    Ligue a TV Box com o cartão inserido.

    No menu do Multitool, selecione a opção Write image to NAND.

    Escolha a imagem que você copiou para a pasta images/.

    Aguarde a finalização da gravação e remova o cartão.

✅ Pronto!

Agora a sua TV Box está com o sistema instalado e pode iniciar direto da NAND com o novo sistema (como LibreELEC).
