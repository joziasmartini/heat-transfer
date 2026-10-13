# Heat Transfer

Simulador e resolvedor numérico interativo concebido para calcular e visualizar a **transferência de calor tridimensional (3D) em regime estacionário**, resolvendo a **Equação de Laplace**.

A aplicação está disponível em [laplace.futuresystems.tech](https://laplace.futuresystems.tech).

## Como executar

Primeiro, instale as dependências:

```bash
npm install
```

Em seguida, execute o servidor de desenvolvimento:

```bash
npm run dev
# ou
yarn dev
# ou
pnpm dev
# ou
bun dev
```

Abra [http://localhost:3000](http://localhost:3000) no navegador para ver o resultado.

Você pode começar a editar a página modificando `app/page.tsx`. A página é atualizada automaticamente conforme você edita o arquivo.

## Funcionalidades

### Fundamento Matemático e Numérico

- Utiliza o **Método das Diferenças Finitas** discretizando o domínio 3D.
- Resolve o sistema pelo **método iterativo de Gauss-Seidel**, no qual cada ponto interno $P_I$ é calculado pela média aritmética dos seus 6 vizinhos contíguos (Norte, Sul, Oeste, Leste, Superior e Inferior):

$$P_I = \frac{P_N + P_S + P_O + P_L + P_{\text{SUP}} + P_{\text{INF}}}{6}$$

### Condições de Contorno e Parâmetros

- Permite definir as temperaturas fixas nas 6 faces do bloco tridimensional (Superior, Inferior, Frente, Trás, Esquerda e Direita).
- Inclui definições de tolerância para o critério de convergência numérica (ex.: $0.001$).

### Visualização Tridimensional e Gráfica

- **Malha 3D**: Exibe o sólido tridimensional com a distribuição espacial de temperaturas, isotermas e linhas de fluxo.
- **Gráfico de Evolução das Temperaturas**: Mapeia o histórico do valor da temperatura em pontos de monitorização ao longo das iterações.

### Controlo de Execução

- Oferece opções para redefinir os nós, executar o cálculo **passo a passo** (iteração por iteração) ou **calcular até à convergência** automática.

## Saiba mais

Para aprender mais sobre o Next.js, consulte os seguintes recursos:

- [Documentação do Next.js](https://nextjs.org/docs) - aprenda sobre recursos e API do Next.js.
- [Aprenda Next.js](https://nextjs.org/learn) - tutorial interativo de Next.js.

## Deploy

A versão publicada está disponível em [laplace.futuresystems.tech](https://laplace.futuresystems.tech). Para saber mais sobre o deploy de aplicações Next.js, consulte a [documentação de deploy do Next.js](https://nextjs.org/docs/app/building-your-application/deploying).
