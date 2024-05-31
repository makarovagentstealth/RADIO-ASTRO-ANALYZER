### README.md

# Analisador de Radiofrequência

## Visão Geral

O Analisador de Radiofrequência é uma ferramenta baseada em Ruby projetada para analisar e decodificar frequências de rádio emitidas por objetos astronômicos. Esta ferramenta utiliza constantes físicas fundamentais e equações matemáticas para fornecer cálculos precisos sem a necessidade de observatórios ou radiotelescópios complexos e invasivos.

## Funcionalidades

- **Calcular Potência Recebida**: Calcula a potência recebida de um sinal transmitido a uma determinada distância considerando o ganho da antena e os fatores de atenuação.
- **Potência de Radiação Rayleigh-Jeans**: Calcula a potência de radiação com base na lei de Rayleigh-Jeans.
- **Potência de Radiação Planck**: Calcula a potência de radiação com base na lei de Planck.
- **Configuração Fácil de Usar**: Lê a configuração de um arquivo JSON simples, facilitando o ajuste de parâmetros e a realização de diversas análises.

## Como Funciona

A ferramenta lê os parâmetros de entrada de um arquivo JSON (`payload.json`) que contém detalhes importantes como frequência central, potência transmitida, ganho da antena, fator de atenuação, distância e temperatura. Usando esses parâmetros, realiza cálculos para determinar:

- A potência recebida do sinal transmitido.
- A potência de radiação emitida, calculada usando as leis de Rayleigh-Jeans e Planck.

## Fundamentos Matemáticos

A ferramenta aplica constantes físicas e equações conhecidas para obter resultados precisos:

1. **Velocidade da Luz (c)**: `299792458 m/s`
2. **Constante de Boltzmann (k)**: `1.380649e-23 J/K`
3. **Constante de Planck (h)**: `6.62607015e-34 J s`

### Principais Equações:

- **Potência Recebida (P<sub>r</sub>)**:
  \[
  P_r = \frac{P_{tx} \cdot G_{antena}^2}{4 \cdot \pi \cdot d^2 \cdot F_{atenuacao}}
  \]

- **Potência de Radiação Rayleigh-Jeans (P<sub>rj</sub>)**:
  \[
  P_{rj} = \frac{2 \cdot \pi \cdot k \cdot T \cdot f^2}{c^2}
  \]

- **Potência de Radiação Planck (P<sub>p</sub>)**:
  \[
  P_p = \frac{h \cdot f}{e^{\frac{h \cdot f}{k \cdot T}} - 1}
  \]

## Instalação

Para usar o Analisador de Radiofrequência, siga estes passos:

1. Certifique-se de ter o Ruby instalado. Você pode baixá-lo no [site oficial do Ruby](https://www.ruby-lang.org/en/downloads/).

2. Clone este repositório ou baixe os arquivos do script.

3. Coloque os arquivos `exploit.rb` e `payload.json` no mesmo diretório.

4. Configure seu `payload.json` com os parâmetros necessários:

   ```json
   {
     "frequencia_central": 1.0e10,
     "potencia_transmitida": 10,
     "ganho_antena": 2,
     "fator_atenuacao": 1,
     "distancia": 1000,
     "temperatura": 300
   }
   ```

## Uso

1. Abra seu terminal ou prompt de comando.
2. Navegue até o diretório que contém `exploit.rb` e `payload.json`.
3. Execute o script com o seguinte comando:

   ```sh
   ruby exploit.rb
   ```

O script lerá a configuração do `payload.json`, realizará os cálculos e exibirá os resultados:

- Potência recebida
- Potência de radiação (Rayleigh-Jeans)
- Potência de radiação (Planck)

## Exemplo de Saída

```
Potência recebida: 3.183098861837907e-06
Potência de radiação (Rayleigh-Jeans): 3.709268162215201e-20
Potência de radiação (Planck): 6.62607015e-24
```

## Conclusão

O Analisador de Radiofrequência oferece uma maneira precisa e amigável de analisar frequências de rádio astronômicas sem a necessidade de equipamentos caros e complexos. Utilizando constantes fundamentais e equações matemáticas, esta ferramenta entrega resultados precisos de forma eficiente.

Sinta-se à vontade para contribuir com o projeto ou sugerir melhorias abrindo uma issue ou um pull request no repositório. Boa análise!
