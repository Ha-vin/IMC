def calcular_imc(peso, altura):
    imc = peso / (altura ** 2)
    return imc

def classificar_imc(imc):
    if imc < 18.5:
        return "Abaixo do peso"
    elif 18.5 <= imc < 24.9:
        return "Peso normal"
    elif 25 <= imc < 29.9:
        return "Sobrepeso"
    elif 30 <= imc < 39.9:
        return "Obesidade"
    else:
        return "Obesidade grave"

def converter_para_metros(altura, unidade):
    if unidade.lower() == 'cm':
        return altura / 100  # Converte de centímetros para metros
    return altura  # Assume que a altura já está em metros

def converter_para_kg(peso, unidade):
    if unidade.lower() == 'lb':
        return peso * 0.453592  # Converte de libras para kg
    return peso  # Assume que o peso já está em kg

        
  def main():
    print("Bem-vindo à Calculadora de IMC!")
    try:
        peso = float(input("Digite seu peso: "))
        unidade_peso = input("Qual unidade está usando? (kg ou lb): ").strip().lower()
        
  altura = float(input("Digite sua altura: "))
        unidade_altura = input("Qual unidade está usando? (m ou cm): ").strip().lower()
        
        # Converte as unidades
   peso_kg = converter_para_kg(peso, unidade_peso)
        altura_metro = converter_para_metros(altura, unidade_altura)

   if peso_kg <= 0 or altura_metro <= 0:
            print("Valores inválidos! Peso e altura devem ser positivos.")
            return
        
   imc = calcular_imc(peso_kg, altura_metro)
        classificacao = classificar_imc(imc)
        
   print(f"\nSeu IMC é: {imc:.2f}")
        print(f"Classificação: {classificacao}")
    
   except ValueError:
        print("Por favor, insira um número válido.")

if __name__ == "__main__":
    main()

if __name__ == "__main__":
    main()
