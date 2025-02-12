import math
import tkinter as tk
from tkinter import messagebox

def calcular():
    try:
        resultado = eval(entry.get())
        label_resultado.config(text = f"Resultado: {resultado}")
    except:
        messagebox.showerror("Erro", "Expressão inválida")

def limpar():
    entry.delete(0, tk.END)
    label_resultado.config(text = "")

janela = tk.Tk()
janela.title("Calculadora Científica")

entry = tk.Entry(janela)
entry.grid(row=0, column=0, columnspan=4)

botao_calcular = tk.Button(janela, text="Calcular", command=calcular)
botao_calcular.grid(row=1, column=0, columnspan=2)

botao_limpar = tk.Button(janela, text="Limpar", command=limpar)
botao_limpar.grid(row=1, column=2, columnspan=2)

label_resultado = tk.Label(janela, text="")
label_resultado.grid(row=2, column=0, columnspan=4)

janela.mainloop()

