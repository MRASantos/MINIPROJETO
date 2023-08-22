import PySimpleGUI as sg

def processamento(valores):
    # Simulação de um processamento interdisciplinar qualquer
    resultado = f"Processamento dos valores: {', '.join(valores)}"
    return resultado

layout = [
    [sg.Text("Projeto PyInterdisciplina", font=("Helvetica", 16))],
    [sg.Text("Valor 1:"), sg.InputText(key="valor1")],
    [sg.Text("Valor 2:"), sg.InputText(key="valor2")],
    [sg.Text("Valor 3:"), sg.InputText(key="valor3")],
    [sg.Button("Processar"), sg.Button("Sair")],
]

window = sg.Window("Projeto PyInterdisciplina", layout)

while True:
    event, values = window.read()
    
    if event == sg.WINDOW_CLOSED or event == "Sair":
        break
    elif event == "Processar":
        entradas = [values["valor1"], values["valor2"], values["valor3"]]
        resultado = processamento(entradas)
        sg.popup(f"Resultado do Processamento:\n\n{resultado}")
        
window.close()
