
sistema de gestão em python.

import pyodbc
import tkinter as tk
from tkinter import *
from tkinter import ttk

dadosConexao = ("Driver={SQLite3 ODBC Driver};Server=hostname;Database=cliente_cadastro.db")


conexao = pyodbc.connect(dadosConexao)

conexao.execute("Select * From Cliente")

cursor = conexao.cursor()

print("executando login")

def inicializar_variaveis_globais():
    global cliente_nome, endereço_cadastrar, contato_cadastrar, vicios_dados, var1, var2, var3, var4, var5, var6, var7, var8, var9, var10, var11, var12, var14, var15, var16, var17, var18, var19, var20, var21, var22, var23, var24, var25, var26, var27, 
    Procedimento_cadastrar, Valor_cadastrar
    cliente_nome = ""
    endereço_cadastrar = ""
    contato_cadastrar = ""
    vicios_dados = ""
    var1 = tk.IntVar()
    var2 = tk.IntVar()
    var3 = tk.IntVar()
    var4 = tk.IntVar()
    var5 = tk.IntVar()
    var6 = tk.IntVar()
    var7 = tk.IntVar()
    var8 = tk.IntVar()
    var9 = tk.IntVar()
    var10 = tk.IntVar()
    var11 = tk.IntVar()
    var12 = tk.IntVar()
    var14 = tk.IntVar()
    var15 = tk.IntVar()
    var16 = tk.IntVar()
    var17 = tk.IntVar()
    var18 = tk.IntVar()
    var19 = tk.IntVar()
    var20 = tk.IntVar()
    var21 = tk.IntVar()
    var22 = tk.IntVar()
    var23 = tk.IntVar()
    var24 = tk.IntVar()
    var25 = tk.IntVar()
    var26 = tk.IntVar()
    var27 = tk.IntVar()
    Procedimento_cadastrar = ""
    Valor_cadastrar = ""

def listar_dados():
            #limpa dos valores da treeview
    for i in treeview.get_children():      
        treeview.delete(i)
    cursor.execute("Select * From Cliente")
            #armazena os valores mencionados no banco de dados
    valores = cursor.fetchall()
    for valor in valores:
        treeview.insert("", "end", values=(valor[0], valor[1], valor[2], valor[3], valor[30], valor[31]))

janela = Tk()
janela.title("Cadastro de clientes")

janela.configure(bg="#F5DEB3")

largura_janela = 1000
altura_janela= 800

largura_tela = janela.winfo_screenwidth()
altura_tela = janela.winfo_screenheight()

pos_x = (largura_tela // 2) - (largura_janela // 2)
pos_y = (altura_tela // 2) - (altura_janela // 2)

janela.geometry('{}x{}+{}+{}'.format(largura_janela, altura_janela, pos_x, pos_y))

menu_barra = Menu(janela)
janela.configure(menu=menu_barra)

janela.attributes("-fullscreen", True)

menu_barra = Menu(janela)
janela.configure(menu=menu_barra)


Label(janela, text="Nome do Cliente: ", font="Arial 16", bg="#F5DEB3").grid(row=0, column=2, padx=10,pady=10)
nome_cliente = Entry(janela, font="Arial 16")
nome_cliente.grid(row=0, column=3, padx=10, pady=10)

Label(janela, text="Procedimento: ", font="Arial 16", bg="#F5DEB3").grid(row=0, column=5, padx=10,pady=10)
novo_Procedimento = Entry(janela, font="Arial 16")
novo_Procedimento.grid(row=0, column=6, padx=10, pady=10)


def cadastrar():
    global cliente_nome, endereço_cadastrar, contato_cadastrar, vicios_dados, var1, var2, var3, var4, var5, var6, var7, var8, var9, var10, var11, var12, var14, var15, var16, var17, var18, var19, var20, var21, var22, var23, var24, var25, var26, var27, Procedimento_cadastrar, Valor_cadastrar
    def on_canvas_configure(event):
        canvas.configure(scrollregion=canvas.bbox("all"))
  janela_cadastrar = Tk()
  janela_cadastrar.title("Cadastro de Informações")
  largura_janela = 1000
  altura_janela= 700
    largura_tela = janela_cadastrar.winfo_screenwidth()
    altura_tela = janela_cadastrar.winfo_screenheight()
    pos_x = (largura_tela // 2) - (largura_janela // 2)
    pos_y = (altura_tela // 2) - (altura_janela // 2)
    janela_cadastrar.geometry('{}x{}+{}+{}'.format(largura_janela, altura_janela, pos_x, pos_y))    
    # Crie um Frame para os widgets
    frame = tk.Frame(janela_cadastrar, bg="#F5DEB3")
    frame.pack(fill="both", expand=True)
    # Crie um Canvas para conter os widgets com uma barra de rolagem
    canvas = tk.Canvas(frame)
    scrollbar = ttk.Scrollbar(frame, orient="vertical", command=canvas.yview)
    canvas.configure(yscrollcommand=scrollbar.set)
    canvas.pack(side="left", fill="both", expand=True)
    scrollbar.pack(side="right", fill="y")
    # Crie um Frame para os widgets dentro do Canvas
    inner_frame = tk.Frame(canvas, bg="#F5DEB3")
    canvas.create_window((0, 0), window=inner_frame, anchor="nw")
    # Adicione os widgets
    Label(inner_frame, text="Nome do Cliente:", font=("Arial", 16), bg="#F5DEB3").grid(row=0, column=0, padx=10, pady=10, sticky="W")
    cliente_nome = Entry(inner_frame, font=("Arial", 16))
    cliente_nome.grid(row=0, column=1, padx=10, pady=10)
    Label(inner_frame, text="Endereço: ", font=("Arial", 16), bg="#F5DEB3").grid(row=1, column=0, padx=10, pady=10, sticky="W")
    endereço_cadastrar = Entry(inner_frame, font=("Arial", 16))
    endereço_cadastrar.grid(row=1, column=1, padx=10, pady=10)
    Label(inner_frame, text="Contato(email ou tel)", font=("Arial", 16), bg="#F5DEB3").grid(row=2, column=0, padx=10, pady=10, sticky="W")
    contato_cadastrar = Entry(inner_frame, font=("Arial", 16))
    contato_cadastrar.grid(row=2, column=1, padx=10, pady=10)
    Label(inner_frame, text="Fumante:", font=("Arial", 16), bg="#F5DEB3").grid(row=3, column=0, padx=10, pady=10, sticky="W")
    vicios_dados = Entry(inner_frame, font=("Arial", 16))
    vicios_dados.grid(row=3, column=1, padx=10, pady=10)
    Label(inner_frame, text="Biótipo Cutâneo", font=("Arial", 28), bg="#F5DEB3").grid(row=4, column=0, padx=10, pady=10, sticky="W")
    var1 = IntVar()
    Checkbutton(inner_frame, text="Pele Normal (Eudérmica)", font=("Arial", 12), bg="#F5DEB3", variable=var1, onvalue=1, offvalue=0, command=salvar_dados).grid(row=5, column=0, stick="w")
    var2 = IntVar()
    Checkbutton(inner_frame, text="Pele Mista", font=("Arial", 12), bg="#F5DEB3", variable=var2, onvalue=1, offvalue=0, command=salvar_dados).grid(row=5, column=1, stick="w")
    var3 = IntVar()
    Checkbutton(inner_frame, text="Pele Lipídica", font=("Arial", 12), bg="#F5DEB3", variable=var3, onvalue=1, offvalue=0, command=salvar_dados).grid(row=6, column=0, stick="w"
    var4 = IntVar()
    Checkbutton(inner_frame, text="Pele Atípica", font=("Arial", 12), bg="#F5DEB3", variable=var4, onvalue=1, offvalue=0, command=salvar_dados).grid(row=6, column=1, stick="w")
    Label(inner_frame, text="Desequilíbrios", font=("Arial", 28), bg="#F5DEB3").grid(row=8, column=0, padx=10, pady=10, sticky="W")
    var5 = IntVar()
    Checkbutton(inner_frame, text="Pele Desidratada", font=("Arial", 12), bg="#F5DEB3", variable=var5, onvalue=1, offvalue=0, command=salvar_dados).grid(row=9, column=0, stick="w")
    var6 = IntVar()
    Checkbutton(inner_frame, text="Pele Sensível", font=("Arial", 12), bg="#F5DEB3", variable=var6, onvalue=1, offvalue=0, command=salvar_dados).grid(row=9, column=1, stick="w")
    var7 = IntVar()
    Checkbutton(inner_frame, text="Pele Reativa", font=("Arial", 12), bg="#F5DEB3", variable=var7, onvalue=1, offvalue=0, command=salvar_dados).grid(row=9, column=2, stick="w")
    var8 = IntVar()
    Checkbutton(inner_frame, text="Pele com acne", font=("Arial", 12), bg="#F5DEB3", variable=var8, onvalue=1, offvalue=0, command=salvar_dados).grid(row=10, column=2, stick="w")
    var9 = IntVar()
    Checkbutton(inner_frame, text="Acne inflamatória", font=("Arial", 12), bg="#F5DEB3", variable=var9, onvalue=1, offvalue=0, command=salvar_dados).grid(row=10, column=0,stick="w")
    var10 = IntVar()
    Checkbutton(inner_frame, text="Pele com Manchas", font=("Arial", 12), bg="#F5DEB3", variable=var10, onvalue=1, offvalue=0, command=salvar_dados).grid(row=11, column=1, stick="w")
    var11 = IntVar()
    Checkbutton(inner_frame, text="Manchas Espalhadas", font=("Arial", 12), bg="#F5DEB3", variable=var11, onvalue=1, offvalue=0, command=salvar_dados).grid(row=10, column=1, stick="w")
    var12 = IntVar()
    Checkbutton(inner_frame, text="Melasma", font=("Arial", 12), bg="#F5DEB3", variable=var12, onvalue=1, offvalue=0, command=salvar_dados).grid(row=11, column=0, stick="w")
    Label(inner_frame, text="Presença de Rugas", font=("Arial", 28), bg="#F5DEB3").grid(row=12, column=0, padx=10, pady=10, sticky="W")
    var14 = IntVar()
    Checkbutton(inner_frame, text="Suave", font=("Arial", 12), bg="#F5DEB3", variable=var14, onvalue=1, offvalue=0, command=salvar_dados).grid(row=13, column=0, sticky="W")
    var15 = IntVar()
    Checkbutton(inner_frame, text="Moderada", font=("Arial", 12), bg="#F5DEB3", variable=var15, onvalue=1, offvalue=0, command=salvar_dados).grid(row=13, column=1, sticky="W")
    var16 = IntVar()
    Checkbutton(inner_frame, text="Avançada", font=("Arial", 12), bg="#F5DEB3", variable=var16, onvalue=1, offvalue=0, command=salvar_dados).grid(row=14, column=0, sticky="W")
    var17 = IntVar()
    Checkbutton(inner_frame, text="Severa", font=("Arial", 12), bg="#F5DEB3", variable=var17, onvalue=1, offvalue=0, command=salvar_dados).grid(row=14, column=1, sticky="W")
    Label(inner_frame, text="Intensidade de Rugas", font=("Arial", 28), bg="#F5DEB3").grid(row=15, column=0, padx=10, pady=10, sticky="W")
    var18 = IntVar()
    Checkbutton(inner_frame, text="Rugas de Expressão (30+) - Periorbitais/Glabela", font=("Arial", 12), bg="#F5DEB3", variable=var18, onvalue=1, offvalue=0, command=salvar_dados).grid(row=16, column=0, sticky="W")
    var19 = IntVar()
    Checkbutton(inner_frame, text="Rugas Estáticas (40+) - Sulco Nasolabial/Bolsas Oculares", font=("Arial", 12), bg="#F5DEB3", variable=var19, onvalue=1, offvalue=0, command=salvar_dados).grid(row=16, column=1, sticky="W")
    var20 = IntVar()
    Checkbutton(inner_frame, text="Rugas Gravitacionais (50+) - Labiais/Contorno Mandibular", font=("Arial", 12), bg="#F5DEB3", variable=var20, onvalue=1, offvalue=0, command=salvar_dados).grid(row=17, column=0, sticky="W")
    var21 = IntVar()
    Checkbutton(inner_frame, text="Rugas Compostas (60+) - Generalizadas/Perda Volumétrica", font=("Arial", 12), bg="#F5DEB3", variable=var21, onvalue=1, offvalue=0, command=salvar_dados).grid(row=17, column=1, sticky="W")
    Label(inner_frame, text="Fototipo", font=("Arial", 28), bg="#F5DEB3").grid(row=18, column=0, padx=10, pady=10, sticky="W")
    var22 = IntVar()
    Checkbutton(inner_frame, text="I - Branco/Loiro-nunca bronzeia", font=("Arial", 12), bg="#F5DEB3", variable=var22, onvalue=1, offvalue=0, command=salvar_dados).grid(row=19, column=0, sticky="W")
    var23 = IntVar()
    Checkbutton(inner_frame, text="II - Branco/Dificilmente bronzeia", font=("Arial", 12), bg="#F5DEB3", variable=var23, onvalue=1, offvalue=0, command=salvar_dados).grid(row=19, column=1, sticky="W")
    var24 = IntVar()
    Checkbutton(inner_frame, text="III - Moreno Claro/bronzeia moderadamente", font=("Arial", 12), bg="#F5DEB3", variable=var24, onvalue=1, offvalue=0, command=salvar_dados).grid(row=20, column=0, sticky="W")
    var25 = IntVar()
    Checkbutton(inner_frame, text="IV - Moreno Moderado - bronzeia facilmente", font=("Arial", 12), bg="#F5DEB3", variable=var25, onvalue=1, offvalue=0, command=salvar_dados).grid(row=20, column=1, sticky="W")
    var26 = IntVar()
    Checkbutton(inner_frame, text="V - Moreno Escuroo - bronzeia intensamente", font=("Arial", 12), bg="#F5DEB3", variable=var26, onvalue=1, offvalue=0, command=salvar_dados).grid(row=21, column=0, sticky="W")
    var27 = IntVar()
    Checkbutton(inner_frame, text="VI - Negro - não se queima", font=("Arial", 12), bg="#F5DEB3", variable=var27, onvalue=1, offvalue=0, command=salvar_dados).grid(row=21, column=1, sticky="W")
    Label(inner_frame, text="Procedimento:", font=("Arial", 18), bg="#F5DEB3").grid(row=22, column=0, padx=10, pady=10, sticky="W")
    Procedimento_cadastrar = Entry(inner_frame, font=("Arial", 18))
    Procedimento_cadastrar.grid(row=22, column=1, padx=10, pady=10, stick="w")
    Label(inner_frame, text="Valor do Tratamento:", font=("Arial", 18), bg="#F5DEB3").grid(row=23, column=0, padx=10, pady=10, sticky="W")
    Valor_cadastrar = Entry(inner_frame, font=("Arial", 18))
    Valor_cadastrar.grid(row=23, column=1, padx=10, pady=10, stick="w")
    botao_salvar_dados = Button(inner_frame, text="Salvar", font=("Arial 12"), command=salvar_dados)
    botao_salvar_dados.grid(row=24, column=0, padx=10, pady=10, stick="NSEW")
    botao_cancelar_dados = Button(inner_frame, text="cancelar", font=("Arial 12"), command=janela_cadastrar.destroy)
    botao_cancelar_dados.grid(row=24, column=1, padx=10, pady=10, stick="NSEW")
    # Configure a função para atualizar a geometria do Canvas
    inner_frame.bind("<Configure>", on_canvas_configure)
    janela_cadastrar.mainloop()


def salvar_dados():     
        novo_cadastro = (
        cliente_nome.get(),
        endereço_cadastrar.get(),
        contato_cadastrar.get(),
        vicios_dados.get(),  # Correção aqui
        var1.get(),
        var2.get(),
        var3.get(),
        var4.get(),
        var5.get(),
        var6.get(),
        var7.get(),
        var8.get(),
        var9.get(),
        var10.get(),
        var11.get(),
        var12.get(),
        var14.get(),
        var15.get(),
        var16.get(),
        var17.get(),
        var18.get(),
        var19.get(),
        var20.get(),
        var21.get(),
        var22.get(),
        var23.get(),
        var24.get(),
        var25.get(),
        var26.get(),
        var27.get(),
        Procedimento_cadastrar.get(),
        Valor_cadastrar.get()
    )                              
        cursor.execute("INSERT INTO Cliente (Nome, Endereço, Contato, Fumante, NORMAL, MISTA, LIPIDICA, ATIPICA, DESIDRATADA, SENSIVEL, REATIVA, ACNE, INFLAMATORIA, MANCHAS, ESPALHADAS, MELASMA, SUAVE, MODERADA, AVANCADA, SEVERA, RC30, RC40, RC50, RC60, I, II, III, IV, V, VI, Procedimento, Valor) values (?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?)", novo_cadastro)
        conexao.commit()
        listar_dados()
        cursor.execute("SELECT * From Cliente")
        print("dados cadastrados com sucesso")
        janela_cadastrar.destroy()

botao_gravar = Button(janela, text="novo", bg="#D71F1F", command=cadastrar, font="Arial 26")
botao_gravar.grid(row=5, column=1, columnspan=2, stick="ES")

style = ttk.Style(janela)

treeview = ttk.Treeview(janela, style="mystyle.Treeview")
style.theme_use("default")


style.configure("mystyle.Treeview", font=("Arial", 14))

def adicionar_registro():
    novo_registro = (
        cliente_nome.get(),
        endereço_cadastrar.get(),
        contato_cadastrar.get(),
        vicios_dados.get(),
        var1.get(),
        var2.get(),
        var3.get(),
        var4.get(),
        var5.get(),
        var6.get(),
        var7.get(),
        var8.get(),
        var9.get(),
        var10.get(),
        var11.get(),
        var12.get(),
        var14.get(),
        var15.get(),
        var16.get(),
        var17.get(),
        var18.get(),
        var19.get(),
        var20.get(),
        var21.get(),
        var22.get(),
        var23.get(),
        var24.get(),
        var25.get(),
        var26.get(),
        var27.get(),
        Procedimento_cadastrar.get(),
        Valor_cadastrar.get()
    ) 
    treeview.insert('', 'end', values=novo_registro)

# Criando a Treeview com as colunas correspondentes aos widgets
treeview = ttk.Treeview(janela, columns=("Nome", "Endereço", "Contato", "Vícios", "Procedimento", "Valor"), show="headings", height=20)

# Configurando os cabeçalhos das colunas
treeview.heading("Nome", text="Nome")
treeview.heading("Endereço", text="Endereço")
treeview.heading("Contato", text="Contato")
treeview.heading("Vícios", text="Vícios")
treeview.heading("Procedimento", text="Procedimento")
treeview.heading("Valor", text="Valor")

# Configurando as larguras das colunas
treeview.column("#0", width=0)
treeview.column("Nome", width=10)
treeview.column("Endereço", width=10)
treeview.column("Contato", width=10)
treeview.column("Vícios", width=10)
treeview.column("Procedimento", width=10)
treeview.column("Valor", width=10)

# Inserindo a Treeview na janela
treeview.grid(row=4, column=0, columnspan=6, stick="NSEW")

listar_dados()

def editar_dados(event):
    global cliente_nome, endereço_cadastrar, contato_cadastrar, vicios_dados, var1, var2, var3, var4, var5, var6, var7, var8, var9, var10, var11, var12, var14, var15, var16, var17, var18, var19, var20, var21, var22, var23, var24, var25, var26, var27, Procedimento_cadastrar, Valor_cadastrar
    def on_canvas_configure(event):
        canvas.configure(scrollregion=canvas.bbox("all"))
    janela_cadastrar = Tk()
    janela_cadastrar.title("Cadastro de Informações")
    largura_janela = 1000
    altura_janela= 700
    largura_tela = janela_cadastrar.winfo_screenwidth()
    altura_tela = janela_cadastrar.winfo_screenheight()
    pos_x = (largura_tela // 2) - (largura_janela // 2)
    pos_y = (altura_tela // 2) - (altura_janela // 2)
    janela_cadastrar.geometry('{}x{}+{}+{}'.format(largura_janela, altura_janela, pos_x, pos_y))   
    
   
      # Crie um Frame para os widgets
frame = tk.Frame(janela_cadastrar, bg="#F5DEB3")
frame.pack(fill="both", expand=True)
    # Crie um Canvas para conter os widgets com uma barra de rolagem
canvas = tk.Canvas(frame)
scrollbar = ttk.Scrollbar(frame, orient="vertical", command=canvas.yview)
canvas.configure(yscrollcommand=scrollbar.set)
canvas.pack(side="left", fill="both", expand=True)
scrollbar.pack(side="right", fill="y")

    # Crie um Frame para os widgets dentro do Canvas
inner_frame = tk.Frame(canvas, bg="#F5DEB3")
canvas.create_window((0, 0), window=inner_frame, anchor="nw")

    # Adicione os widgets
Label(inner_frame, text="Nome do Cliente:", font=("Arial", 16), bg="#F5DEB3").grid(row=0, column=0, padx=10, pady=10, sticky="W")
cliente_nome = Entry(inner_frame, font=("Arial", 16))
cliente_nome.grid(row=0, column=1, padx=10, pady=10)
    Label(inner_frame, text="Endereço: ", font=("Arial", 16), bg="#F5DEB3").grid(row=1, column=0, padx=10, pady=10, sticky="W")
    endereço_cadastrar = Entry(inner_frame, font=("Arial", 16))
    endereço_cadastrar.grid(row=1, column=1, padx=10, pady=10)
    Label(inner_frame, text="Contato(email ou tel)", font=("Arial", 16), bg="#F5DEB3").grid(row=2, column=0, padx=10, pady=10, sticky="W")
    contato_cadastrar = Entry(inner_frame, font=("Arial", 16))
    contato_cadastrar.grid(row=2, column=1, padx=10, pady=10)
    Label(inner_frame, text="Fumante:", font=("Arial", 16), bg="#F5DEB3").grid(row=3, column=0, padx=10, pady=10, sticky="W")
    vicios_dados = Entry(inner_frame, font=("Arial", 16))
    vicios_dados.grid(row=3, column=1, padx=10, pady=10)
    Label(inner_frame, text="Biótipo Cutâneo", font=("Arial", 28), bg="#F5DEB3").grid(row=4, column=0, padx=10, pady=10, sticky="W")
    var1 = IntVar()
    Checkbutton(inner_frame, text="Pele Normal (Eudérmica)", font=("Arial", 12), bg="#F5DEB3", variable=var1, onvalue=1, offvalue=0, command=salvar_dados).grid(row=5, column=0, stick="w")
    var2 = IntVar()
    Checkbutton(inner_frame, text="Pele Mista", font=("Arial", 12), bg="#F5DEB3", variable=var2, onvalue=1, offvalue=0, command=salvar_dados).grid(row=5, column=1, stick="w")
    var3 = IntVar()
    Checkbutton(inner_frame, text="Pele Lipídica", font=("Arial", 12), bg="#F5DEB3", variable=var3, onvalue=1, offvalue=0, command=salvar_dados).grid(row=6, column=0, stick="w")
    var4 = IntVar()
    Checkbutton(inner_frame, text="Pele Atípica", font=("Arial", 12), bg="#F5DEB3", variable=var4, onvalue=1, offvalue=0, command=salvar_dados).grid(row=6, column=1, stick="w")
    Label(inner_frame, text="Desequilíbrios", font=("Arial", 28), bg="#F5DEB3").grid(row=8, column=0, padx=10, pady=10, sticky="W")
    var5 = IntVar()
    Checkbutton(inner_frame, text="Pele Desidratada", font=("Arial", 12), bg="#F5DEB3", variable=var5, onvalue=1, offvalue=0, command=salvar_dados).grid(row=9, column=0, stick="w")
    var6 = IntVar()
    Checkbutton(inner_frame, text="Pele Sensível", font=("Arial", 12), bg="#F5DEB3", variable=var6, onvalue=1, offvalue=0, command=salvar_dados).grid(row=9, column=1, stick="w")
    var7 = IntVar()
    Checkbutton(inner_frame, text="Pele Reativa", font=("Arial", 12), bg="#F5DEB3", variable=var7, onvalue=1, offvalue=0, command=salvar_dados).grid(row=9, column=2, stick="w")
    var8 = IntVar()
    Checkbutton(inner_frame, text="Pele com acne", font=("Arial", 12), bg="#F5DEB3", variable=var8, onvalue=1, offvalue=0, command=salvar_dados).grid(row=10, column=2, stick="w")
    var9 = IntVar()
    Checkbutton(inner_frame, text="Acne inflamatória", font=("Arial", 12), bg="#F5DEB3", variable=var9, onvalue=1, offvalue=0, command=salvar_dados).grid(row=10, column=0,stick="w")
    var10 = IntVar()
    Checkbutton(inner_frame, text="Pele com Manchas", font=("Arial", 12), bg="#F5DEB3", variable=var10, onvalue=1, offvalue=0, command=salvar_dados).grid(row=11, column=1, stick="w")
    var11 = IntVar()
    Checkbutton(inner_frame, text="Manchas Espalhadas", font=("Arial", 12), bg="#F5DEB3", variable=var11, onvalue=1, offvalue=0, command=salvar_dados).grid(row=10, column=1, stick="w")
    var12 = IntVar()
    Checkbutton(inner_frame, text="Melasma", font=("Arial", 12), bg="#F5DEB3", variable=var12, onvalue=1, offvalue=0, command=salvar_dados).grid(row=11, column=0, stick="w")
    Label(inner_frame, text="Presença de Rugas", font=("Arial", 28), bg="#F5DEB3").grid(row=12, column=0, padx=10, pady=10, sticky="W")
    var14 = IntVar()
    Checkbutton(inner_frame, text="Suave", font=("Arial", 12), bg="#F5DEB3", variable=var14, onvalue=1, offvalue=0, command=salvar_dados).grid(row=13, column=0, sticky="W")
    var15 = IntVar()
    Checkbutton(inner_frame, text="Moderada", font=("Arial", 12), bg="#F5DEB3", variable=var15, onvalue=1, offvalue=0, command=salvar_dados).grid(row=13, column=1, sticky="W")
    var16 = IntVar()
    Checkbutton(inner_frame, text="Avançada", font=("Arial", 12), bg="#F5DEB3", variable=var16, onvalue=1, offvalue=0, command=salvar_dados).grid(row=14, column=0, sticky="W")
    var17 = IntVar()
    Checkbutton(inner_frame, text="Severa", font=("Arial", 12), bg="#F5DEB3", variable=var17, onvalue=1, offvalue=0, command=salvar_dados).grid(row=14, column=1, sticky="W")
    Label(inner_frame, text="Intensidade de Rugas", font=("Arial", 28), bg="#F5DEB3").grid(row=15, column=0, padx=10, pady=10, sticky="W")
    var18 = IntVar()
    Checkbutton(inner_frame, text="Rugas de Expressão (30+) - Periorbitais/Glabela", font=("Arial", 12), bg="#F5DEB3", variable=var18, onvalue=1, offvalue=0, command=salvar_dados).grid(row=16, column=0, sticky="W")
    var19 = IntVar()
    Checkbutton(inner_frame, text="Rugas Estáticas (40+) - Sulco Nasolabial/Bolsas Oculares", font=("Arial", 12), bg="#F5DEB3", variable=var19, onvalue=1, offvalue=0, command=salvar_dados).grid(row=16, column=1, sticky="W")
    var20 = IntVar()
    Checkbutton(inner_frame, text="Rugas Gravitacionais (50+) - Labiais/Contorno Mandibular", font=("Arial", 12), bg="#F5DEB3", variable=var20, onvalue=1, offvalue=0, command=salvar_dados).grid(row=17, column=0, sticky="W")
    var21 = IntVar()
    Checkbutton(inner_frame, text="Rugas Compostas (60+) - Generalizadas/Perda Volumétrica", font=("Arial", 12), bg="#F5DEB3", variable=var21, onvalue=1, offvalue=0, command=salvar_dados).grid(row=17, column=1, sticky="W")
    Label(inner_frame, text="Fototipo", font=("Arial", 28), bg="#F5DEB3").grid(row=18, column=0, padx=10, pady=10, sticky="W")
    var22 = IntVar()
    Checkbutton(inner_frame, text="I - Branco/Loiro-nunca bronzeia", font=("Arial", 12), bg="#F5DEB3", variable=var22, onvalue=1, offvalue=0, command=salvar_dados).grid(row=19, column=0, sticky="W")
    var23 = IntVar()
    Checkbutton(inner_frame, text="II - Branco/Dificilmente bronzeia", font=("Arial", 12), bg="#F5DEB3", variable=var23, onvalue=1, offvalue=0, command=salvar_dados).grid(row=19, column=1, sticky="W")
    var24 = IntVar()
    Checkbutton(inner_frame, text="III - Moreno Claro/bronzeia moderadamente", font=("Arial", 12), bg="#F5DEB3", variable=var24, onvalue=1, offvalue=0, command=salvar_dados).grid(row=20, column=0, sticky="W")
    var25 = IntVar()
    Checkbutton(inner_frame, text="IV - Moreno Moderado - bronzeia facilmente", font=("Arial", 12), bg="#F5DEB3", variable=var25, onvalue=1, offvalue=0, command=salvar_dados).grid(row=20, column=1, sticky="W")
    var26 = IntVar()
    Checkbutton(inner_frame, text="V - Moreno Escuroo - bronzeia intensamente", font=("Arial", 12), bg="#F5DEB3", variable=var26, onvalue=1, offvalue=0, command=salvar_dados).grid(row=21, column=0, sticky="W")
    var27 = IntVar()
    Checkbutton(inner_frame, text="VI - Negro - não se queima", font=("Arial", 12), bg="#F5DEB3", variable=var27, onvalue=1, offvalue=0, command=salvar_dados).grid(row=21, column=1, sticky="W")
    Label(inner_frame, text="Procedimento:", font=("Arial", 18), bg="#F5DEB3").grid(row=22, column=0, padx=10, pady=10, sticky="W")
    Procedimento_cadastrar = Entry(inner_frame, font=("Arial", 18))
    Procedimento_cadastrar.grid(row=22, column=1, padx=10, pady=10, stick="w")
    Label(inner_frame, text="Valor do Tratamento:", font=("Arial", 18), bg="#F5DEB3").grid(row=23, column=0, padx=10, pady=10, sticky="W")
    Valor_cadastrar = Entry(inner_frame, font=("Arial", 18))
    Valor_cadastrar.grid(row=23, column=1, padx=10, pady=10, stick="w")
    botao_salvar_dados = Button(inner_frame, text="Salvar", font=("Arial 12"), command=salvar_dados)
    botao_salvar_dados.grid(row=24, column=0, padx=10, pady=10, stick="NSEW")
    botao_cancelar_dados = Button(inner_frame, text="cancelar", font=("Arial 12"), command=janela_cadastrar.destroy)
    botao_cancelar_dados.grid(row=24, column=1, padx=10, pady=10, stick="NSEW")
    # Configure a função para atualizar a geometria do Canvas
    inner_frame.bind("<Configure>", on_canvas_configure)
    janela_cadastrar.mainloop()
    def atualizar_dados():
        novo_cadastro = (cliente_nome.get(), endereço_cadastrar.get(), contato_cadastrar.get(), vicios_dados.get(), var1.get(), var2.get(), var3.get(), var4.get(), var5.get(), var6.get(), var7.get(), var8.get(), var9.get(), var10.get(), var11.get(), var12.get(), var14.get(), var15.get(), var16.get(), var17.get(), var18.get(), var19.get(), var20.get(), var21.get(), var22.get(),  var23.get(), var24.get(),  var25.get(), var26.get(), var27.get(), Procedimento_cadastrar.get(), Valor_cadastrar.get())
        treeview.item(item_selecionado, values=(valores_selecionados[0],novo_cadastro, novo_endereço, novo_contato, novo_vicios, novo_Procedimento, novo_Valor))   
        cursor.execute("UPDATE Cliente SET Nome = ?, NORMAL = ?, MISTA = ?, LIPIDICA = ?, ATIPICA = ?, DESIDRATADA = ?, SENSIVEL = ?, REATIVA = ?, ACNE = ?, INFLAMATORIA = ?, MANCHAS = ?, ESPALHADAS = ?, MELASMA = ?, SUAVE = ?, MODERADA = ?, AVANCADA = ?, SEVERA = ?, RC30 = ?, RC40 = ?, RC50 = ?, RC60 = ?, I = ?, II = ?, III = ?, IV = ?, V = ?, VI = ?, Procedimento = ?, Valor = ?", (novo_cadastro, novo_endereço, novo_contato, nome_produto, valores_selecionados[0]))
        conexao.commit() #gravando no banco de dados
        listar_dados()
        cursor.execute("SELECT * From Cliente")
        janela_editar.destroy()
        print("dados Alterados com sucesso")
        botao_editar_dados = Button(janela_editar, text="ALTERAR", font=("Arial 16"), bg="#008000",fg="#FFFFFF", command=atualizar_dados)
        botao_editar_dados.grid(row=4, column=0, padx=20, pady=20)
   
def deletar_registro(): 
    selected_item = treeview.selection()[0]
    id = treeview.item(selected_item)['values'][0]
    cursor.execute("DELETE FROM Cliente WHERE  Nome = ?", (Nome))
    conexao.commit()
    listar_dados()
    janela_editar.destroy() 
    botao_editar_dados = Button(janela_editar, text="DELETAR", font=("Arial 16"), bg="#FF0000",fg="#FFFFFF", command=deletar_registro)
    botao_editar_dados.grid(row=4, column=1, padx=20, pady=20)
     
treeview.bind("<Double-1>", editar_dados)
   
menu_arquivo = Menu(menu_barra, tearoff=0)
menu_barra.add_cascade(label="Arquivo", menu=menu_arquivo)

menu_arquivo.add_command(label="Cadastrar", command=cadastrar)

menu_arquivo.add_command(label="Sair", command=janela.destroy)

def limpardados():
    for i in treeview.get_children():
        treeview.delete(i)
       
def selecionar_dados(nome_cliente, novo_Procedimento):
    if not nome_cliente.get() and not novo_Procedimento.get():
        listar_dados()
        return
    sql = "SELECT * From CLiente"
    params = []
    if nome cliente.get():     
        sql += " WHERE Nome LIKE ?"
        params.append('%' + nome_cliente.get() + '%')             
    if novo_Procedimento.get():
        if nome_cliente.get():
            sql += " AND"
        else:
            sql += " WHERE"
            sql += " Procedimento LIKE ?"
            params.append('%' + nome_cliente.get() + '%')
    cursor.execute(sql, tuple(params))
    produtos = cursor.fetchall()          
    limpardados()         
    for dado in produtos:          
            treeview.insert('', 'end', values=(dado[0], dado[1], dado[2], dado[3], dado[4], dado[5], dado[6], dado[7], dado[8], dado[9], dado[10], dado[11], dado[12], dado[13], dado[14], dado[15], dado[16], dado[17],  dado[18], dado[19], dado[20], dado[21], dado[22], dado[23], dado[24], dado[25], dado[26], dado[27], dado[28], dado[29], dado[30], dado[31], dado[32], dado[33]))                



nome_cliente.bind('<KeyRelease>', lambda e: selecionar_dados(nome_cliente, novo_Procedimento))
novo_Procedimento.bind('<KeyRelease>', lambda e: selecionar_dados(nome_cliente, novo_Procedimento))

def deletar():
    selected_item = treeview.selection()
    if selected_item:  # Verifica se algum item foi selecionado
        Nome = treeview.item(selected_item[0])['values'][0]
        cursor.execute("DELETE FROM Cliente WHERE Nome = ?", (Nome,))
        conexao.commit()


def salvar_agendamento():
    janela_agendamento = Toplevel()
    janela_agendamento.title("Agendamento")
    cal = Calendar(janela_agendamento)
    cal.grid(row=0, column=0, padx=10, pady=10)
    horarios = ["08:00", "09:00", "10:00", "11:00", "14:00", "15:00", "16:00", "17:00"]
    horario_combobox = ttk.Combobox(janela_agendamento, values=horarios)
    horario_combobox.grid(row=1, column=0, padx=10, pady=10)
    tk.Label(janela_agendamento, text="Nome do Cliente").grid(row=2, column=0, padx=10, pady=10)
    nome_cliente = tk.Entry(janela)
    nome_cliente.grid(row=2, column=1, padx=10, pady=10)
    tk.Label(janela_agendamento, text="Tipo de Serviço").grid(row=3, column=0, padx=10, pady=10)
    tipo_servico = tk.Entry(janela)
    tipo_servico.grid(row=3, column=1, padx=10, pady=10)
    salvar_button = tk.Button(janela_agendamento, text="Salvar Agendamento", command=agendamento)
    salvar_button.grid(row=4, column=0, columnspan=2, padx=10, pady=10)
    def agendamento():
        cliente = nome_cliente.get()
        data = cal.get_date()
        horario = horario_combobox.get()
        servico = tipo_servico.get()
        conn = sqlite3.connect('cliente_cadastro.db')
        cursor = conn.cursor()
        # Inserir o agendamento na tabela
        cursor.execute('INSERT INTO Agendamentos (Nome, Data, Horario, Procedimento) VALUES (?, ?, ?, ?)', (cliente, data, horario, servico))
        # Confirmar a transação e fechar a conexão
        conn.commit()
        conn.close()
        print(f"Data: {data}, Horário: {horario}, Cliente: {cliente}, Serviço: {servico}")
        janela_agendamento.m
        janela_agendamento.destroy()

botao_deletar = Button(janela, text="Deletar", bg="#1FD76F", command=deletar,  font="Arial 26")
botao_deletar.grid(row=5, column=3, stick=N, columnspan=2, pady=5, padx=10)


botao_agendar = Button(janela, text="Agendar", bg="#4F29E8", fg="#000000", command=salvar_agendamento,  font="Arial 26")
botao_agendar.grid(row=5, column=4, stick=N, columnspan=2, pady=5, padx=10)


import tkinter as tk
import sqlite3

class ChatBotApp:
    def __init__(self, root):
        self.root = root
        self.root.title("Athena")
        self.chat_history = []
        self.chatbox = tk.Text(root, wrap=tk.WORD)
        self.chatbox.grid(row=4, column=6, columnspan=2, padx=10, pady=10, sticky="EN")
        self.chatbox.config(state=tk.DISABLED)
        self.user_input = tk.Entry(root)
        self.user_input.grid(row=6, column=6, padx=10, pady=10, sticky="ew")
        self.user_input.bind("<Return>", self.send_message)
        self.send_button = tk.Button(root, text="Enviar", command=self.send_message)
        self.send_button.grid(row=7, column=7, padx=10, pady=10, sticky="ew")
        janela.grid_rowconfigure(0, weight=1)
        janela.grid_columnconfigure(0, weight=1)
        self.db_conn = sqlite3.connect("clientes.db")
        self.db_cursor = self.db_conn.cursor()
    def send_message(self, event=None):
        user_message = self.user_input.get()
        self.add_to_chat("Você:", user_message)
        if user_message.lower() == "calcular":
            self.calculate()
        elif user_message.lower() == "consultar":
            self.query_database()
        elif user_message.lower() == "lista de clientes":
            self.list_clients()
        else:
            bot_response = self.generate_response(user_message)
            self.add_to_chat("Athena:", bot_response)
        self.user_input.delete(0, "end")
    def calculate(self):
        expression = self.user_input.get()
        try:
            result = eval(expression)
            self.add_to_chat("ChatBot:", f"Resultado do cálculo: {result}")
        except:
            self.add_to_chat("ChatBot:", "Erro ao calcular")
    def query_database(self):
        query = "SELECT user_message, bot_response FROM messages"
        self.db_cursor.execute(query)
        results = self.db_cursor.fetchall()
        for row in results:
            self.add_to_chat("Histórico:", f"Você: {row[0]} | ChatBot: {row[1]}"
    def list_clients(self):
        query = "SELECT nome, email, telefone FROM clientes"
        self.db_cursor.execute(query)
        results = self.db_cursor.fetchall()
        self.add_to_chat("ChatBot:", "Lista de Clientes:")
        for row in results:
            self.add_to_chat("Cliente:", f"Nome: {row[0]}, Email: {row[1]}, Telefone: {row[2]}")
    def generate_response(self, user_message):
        responses = {
            "Olá": "Olá! Como posso ajudar?",
            "Como você está?": "Estou bem, obrigado por perguntar!",
            # Adicione mais respostas aqui
        }
        return responses.get(user_message, "Desculpe, não entendi. Pode reformular sua pergunta?")
    def add_to_chat(self, sender, message):
        self.chatbox.config(state=tk.NORMAL)
        self.chatbox.insert(tk.END, sender + " " + message + "\n")
        self.chatbox.config(state=tk.DISABLED)

if __name__ == '__main__':
    janela = (janela)
    app = ChatBotApp(janela)
   janela.mainloop()
