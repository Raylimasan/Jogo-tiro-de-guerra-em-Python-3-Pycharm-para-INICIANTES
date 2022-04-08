# Jogo-tiro-de-guerra-em-Python-3-Pycharm-para-INICIANTES
# Código desenvolvido com conhecimento absorvido do jogo da forca e advinha, o tema foi eu que criei.  (Desculpa alguma falha tenho apenas um mês nesse novo mundo e aceito sugestões de melhoria nos comentários.)

#Apresentação e coleta de informações do jogo
def jogar():
    print('###############################################')
    print('          ##TIRO DE GUERRA##          ')
    print('###############################################')
    nome_jogador = input('Informe seu nome recruta:').upper()
    print('Tente acerta onde esta o alvo com seus tiros!')
    alvo = round(random.random() * 50)
    recarga = 1
   
    
#Escolha de patente

    print('Escolha uma patente, quanto maior for a patente menos munições você terá para acerta o alvo!')
    patente = int(input('(1) Soldado , (2) Tenente, (3) Capitão, (4) Coronel, (5) General, (6) Marechal:'))
    total_de_balas = 0

    if patente == 1:
        total_de_balas = 15
        print('Você tem 15 munições, vamos lá soldado, mostre que você pode ser promovido a Tenente!')
    if patente == 2:
        total_de_balas = 12
        print('Você tem 12 munições, vamos lá tenente, mostre que você pode ser promovido a Capitão!')
    if patente == 3:
        total_de_balas = 9
        print('Você tem 9 munições, vamos lá capitão, mostre que você pode ser promovido a Coronel!')
    if patente == 4:
        total_de_balas = 6
        print('Você tem 6 munições, vamos lá coronel, mostre que você pode ser promovido a Generel!')
    if patente == 5:
        total_de_balas = 3
        print('Você tem 3 munições, vamos lá general, mostre que você pode ser promovido a Marechal !')
    if patente == 6:
        total_de_balas = 1
        print('Você tem 1 munição, vamos lá Marechal, mostre que você merece essa patente!')

#Quantidade de recargas da patente escolhida
#Se o tito for maior, menor ou certeiro

    for recarga in range(1, total_de_balas  + 1):
        print(f'Tiro {recarga} de {total_de_balas}')
        tiro = int(input('Em qual alvo você quer atirar:'))
        if tiro < 1 or tiro > 50:
            print('Tiro fora do alcance, digite um tiro em um raio entre 1 e 50.')
            continue
        if tiro != alvo:
            if tiro > alvo:
                print(f'{nome_jogador} seu tiro foi muito alto, tente um alvo mais baixo!')
            elif tiro < alvo:
                print(f'{nome_jogador} seu tiro foi muito baixo, tente um alvo mais alto!')
        if tiro == alvo:
            print(f'Que tiro certeiro, seu tiro foi no alvo {alvo} e você acertou, '
                  f'PARABÉNS {nome_jogador}!')
            para_ou_continua = int(input("Digite (1) se deseja jogar novamente," (2) se quiser encerrar:"))
            if para_ou_continua == 1:
                    jogar()
            if para_ou_continua == 2:
                print(f'Obrigado por jogar, espero te ver novamente em breve {nome_jogador}!')
                break



if (__name__ == '__main__'):
    jogar()
