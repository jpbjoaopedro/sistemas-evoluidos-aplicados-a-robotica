# Análise de Modelos YOLO em Imagens

Este repositório contém um script em Python (formato Jupyter Notebook) focado em executar e medir o tempo de inferência de diferentes versões do modelo de detecção de objetos YOLO.

## Visão Geral do Código

O código foi desenvolvido para ser executado no ambiente do **Google Colab** e está estruturado nas seguintes etapas:

1. **Instalação e Importação de Bibliotecas:**
   O script começa instalando a biblioteca `ultralytics` para ter acesso aos modelos YOLO. Em seguida, importa ferramentas essenciais como `requests` (para requisições web), `cv2` (OpenCV, para manipulação de imagem), `numpy` (para arrays de dados) e a biblioteca `time` (para cronometrar a execução).

2. **Carregamento da Imagem de Teste:**
   Em vez de fazer o upload manual, o código faz o download de uma imagem de teste (neste caso, do COCO dataset) diretamente através de uma URL usando o `requests`. A resposta é convertida em um array usando `numpy` e decodificada como uma imagem colorida pelo OpenCV.

3. **Seleção e Carregamento do Modelo:**
   O usuário pode selecionar através de um formulário interativo qual versão do modelo YOLO deseja instanciar e testar. As opções disponíveis no código variam em tamanho e complexidade:
   * `yolo26n.pt` (Nano)
   * `yolo26s.pt` (Small)
   * `yolo26m.pt` (Medium)
   * `yolo26l.pt` (Large)
   * `yolo26x.pt` (Extra Large)

4. **Inferência e Cálculo de Tempo:**
   A etapa central do código roda o modelo na imagem carregada (`results = model(img)`). Para medir a performance, o script utiliza a função `time.perf_counter()` para gravar o momento de início (`start`) e de término (`end`) da detecção. A diferença entre esses dois valores imprime no console o tempo exato de inferência em segundos.

5. **Exibição dos Resultados:**
   O script extrai a imagem anotada com as detecções do modelo (`results.plot()`) e a renderiza na tela do Colab usando a função `cv2_imshow` (importada especificamente do `google.colab.patches`).


Bibliotecas utilizadas:
- `ultralytics`
- `opencv-python`
- `numpy`
- `requests`
