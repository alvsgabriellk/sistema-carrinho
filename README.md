# sistema-carrinho


class Produto:

    def __init__(self, nome=None, preço=0  , quantidade=0):
        self.nome = nome
        self.preço = preço
        self.quantidade = quantidade

class Carrinho():

    def __init__(self):
        self.itens = []

    def adicionar_produto(self, produto=None):
        self.itens.append(produto)

    def remover_produto(self, nome=None):
        for produto in self.itens:
            if produto.nome == nome:
                self.itens.remove(produto)
                print(f'Produto removido do carrinho!')
            else:
                print('Produto não encontrado!')

    def listar_produtos(self):
        for i in self.itens:
            print(f'Produto: {i.nome} | Preço: R${i.preço} | Quantidade: {i.quantidade}')

    def calcular_total(self):
        total = 0
        for produto in self.itens:
            total = produto.preço * produto.quantidade
        print(f'Total da compra: R${total:.2f}')



p1 = Produto('Banana', 2.50, 52)
p2 = Produto('Bolo', 17, 12)

carrinho1 = Carrinho()
carrinho2 = Carrinho()
carrinho1.adicionar_produto(p1)
carrinho2.adicionar_produto(p2)



carrinho1.listar_produtos()
carrinho1.calcular_total()
carrinho2.listar_produtos()
carrinho2.calcular_total()


