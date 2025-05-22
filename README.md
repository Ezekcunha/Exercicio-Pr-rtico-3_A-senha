# Exercicio-Pr-rtico-3_A-senha
EXERCÍCIO PRÁTICO 3

Crie um programa que verifique se uma senha é forte. Uma senha forte deve ter pelo menos 8 caracteres e conter pelo menos um número. O programa deve continuar pedindo senhas até que uma válida seja inserida ou o usuário digite 'sair'.

Implementação do programa em Python (Execução do "comando"):
def verificar_senha_forte(senha: str) -> bool:
  """
  Verifica se uma senha é forte de acordo com os critérios:
  - Pelo menos 8 caracteres.
  - Conter pelo menos um número.

  Args:
    senha (str): A senha a ser verificada.

  Returns:
    bool: True se a senha for forte, False caso contrário.
  """
  if len(senha) < 8:
    return False

  contem_numero = False
  for caracter in senha:
    if caracter.isdigit():
      contem_numero = True
      break
  
  return contem_numero

def programa_verificar_senha():
  """
  Programa principal que pede senhas ao usuário e as verifica
  até que uma senha válida seja inserida ou o usuário digite 'sair'.
  """
  print("--- Verificador de Senha Forte ---")
  print("Critérios: Pelo menos 8 caracteres e conter pelo menos um número.")
  print("Digite 'sair' a qualquer momento para encerrar.")

  while True:
    senha = input("\nDigite uma senha: ").strip()

    if senha.lower() == 'sair':
      print("Programa encerrado.")
      break

    if verificar_senha_forte(senha):
      print(f"'{senha}' é uma senha FORTE. Parabéns!")
      break
    else:
      print(f"'{senha}' NÃO é uma senha forte.")
      print("Por favor, tente novamente com uma senha que atenda aos critérios.")

# Para "executar o comando", chame a função principal:
programa_verificar_senha()
