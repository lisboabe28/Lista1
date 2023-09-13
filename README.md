# Lista1
"""Introdução a Orientação a Objetos
1. Adicione mais 2 atributos e 2 métodos à classe Mago.
2. Instancie 3 objetos da classe mago e invoque seus métodos.
3. Crie uma classe Data, com os seguintes atributos: dia, mês e ano. Além do construtor padrão, a
classe deverá ter um construtor personalizado que recebe dia, mês e ano por parâmetro. Essa classe
deve ter também dois métodos: imprimirData, que não recebe parâmetro, e
imprimirDataPorExtenso, que recebe o nome de uma cidade por parâmetro. Ambos os métodos
não retornam dados.
4. Adapte o exercício de revisão (mini-spotify), proponto uma classe Musica. Quais seriam seus
atributos? Quais seriam alguns dos seus possíveis métodos? Como poderíamos representar uma
playlist?"""

                  
class Mago:
    possuiMagia = True

    def __init__(self, nome, idade, escola):
        self.nome = nome 
        self.idade = idade   
        self.escola = escola 
        print('Mago ', self.nome, ' foi criado!')
        self.poderes = []  # Novo atributo para armazenar os poderes do mago
        self.experiencia = 0  # Novo atributo para rastrear a experiência do mago

    def andar(self):
        print('Estou andando')
    
    def falar(self):
        print('Olá amigue! Meu nome é ', self.nome)
        
    def invocarMagia(self):
        print('Invocando magia!')

    def cumprimentar(self, nome):
        print('Olá, ', nome)

    def aprenderPoder(self, poder):
        self.poderes.append(poder)
        print(f'{self.nome} aprendeu o poder {poder}')

    def ganharExperiencia(self, quantidade):
        self.experiencia += quantidade
        print(f'{self.nome} ganhou {quantidade} pontos de experiência. Total: {self.experiencia}')


# Instanciação de um objeto da classe Mago
hp = Mago('Harry Potter', 17, 'Hogwarts')
gd = Mago('Gandalf', 2000, 'Magia Cinza')
#novos 
dumbledore = Mago('Albus Dumbledore', 150, 'Hogwarts')
ron = Mago('Ron Weasley', 18, 'Hogwarts')
hermione = Mago('Hermione Granger', 18, 'Hogwarts')

# Acessando atributos públicos
print(hp.nome)
print(hp.idade)
print(hp.escola)

# Invocando métodos
hp.andar()
hp.falar()
hp.invocarMagia()
hp.cumprimentar("Rossana")

gd.falar()
gd.cumprimentar("Gabriel")

# Utilizando os novos métodos e atributos
hp.aprenderPoder("Expelliarmus")
hp.ganharExperiencia(50)

#novos 
dumbledore.andar()
ron.falar()
hermione.cumprimentar("Harry")
dumbledore.aprenderPoder("Expecto Patronum")
ron.ganharExperiencia(30)


#classe data
class Data:
    def __init__(self, dia=1, mes=1, ano=2000):
        self.dia = dia
        self.mes = mes
        self.ano = ano

    def imprimirData(self):
        print(f'Data: {self.dia}/{self.mes}/{self.ano}')

    def imprimirDataPorExtenso(self, cidade):
        meses = ["Janeiro", "Fevereiro", "Março", "Abril", "Maio", "Junho",
                 "Julho", "Agosto", "Setembro", "Outubro", "Novembro", "Dezembro"]
        mes_extenso = meses[self.mes - 1]
        print(f'Data: {self.dia} de {mes_extenso} de {self.ano} em {cidade}')


# Exemplo de uso da classe Data
data1 = Data(13, 9, 2023)
data1.imprimirData()
data1.imprimirDataPorExtenso("Nova York")

class Musica:
    def __init__(self, titulo, artista, album, duracao):
        self.titulo = titulo
        self.artista = artista
        self.album = album
        self.duracao = duracao

    def reproduzir(self):
        print(f'Tocando: {self.titulo} - {self.artista}')

    def detalhes(self):
        print(f'Título: {self.titulo}')
        print(f'Artista: {self.artista}')
        print(f'Álbum: {self.album}')
        print(f'Duração: {self.duracao} segundos')



#classe musica

class Playlist:
    def __init__(self, nome):
        self.nome = nome
        self.musicas = []

    def adicionarMusica(self, musica):
        self.musicas.append(musica)

    def removerMusica(self, musica):
        if musica in self.musicas:
            self.musicas.remove(musica)

    def listarMusicas(self):
        print(f'Playlist: {self.nome}')
        for i, musica in enumerate(self.musicas, start=1):
            print(f'{i}. {musica.titulo} - {musica.artista}')


# Exemplo de uso das classes Musica e Playlist
musica1 = Musica('Bohemian Rhapsody', 'Queen', 'A Night at the Opera', 354)
musica2 = Musica('Imagine', 'John Lennon', 'Imagine', 183)
musica3 = Musica('Hotel California', 'Eagles', 'Hotel California', 391)

playlist = Playlist('Minha Playlist')
playlist.adicionarMusica(musica1)
playlist.adicionarMusica(musica2)
playlist.adicionarMusica(musica3)

playlist.listarMusicas()

musica2.detalhes()



