# Atividade DDD
 - Nome: Renan Borba Santos          - RA: 8094313
 - Nome: João Vitor Mouro            - RA: 8093252
 - Nome: Deivid Inácio da Silva      - RA: 8093298
 - Nome: Kawan Miguel Oliveira Silva - RA: 8093341

# DDD ( Domain-driven Design )

Design dirigido à domínio

# Domínio: 
  - O domínio escolhido foi o de estudo com ênfase no contexto de tarefas/exercícios(criados pelos professores e respondidos pelos alunos). O sistema estuda-dev, surgiu a partir da necessidade de atender os alunos no ambiente educacional, com o objetivo de facilitar a comunicação entre eles, gerando assim as responsabilidades de criação e devolutiva de atividades  pelo professor e ao aluno a de entregar as atividades.

# Linguagem ubíqua: 
  -usuário -> aluno/professor - tarefas -> exercise - respostas -> answer - grade -> nota

# Entidades: answer, exercise, student e teacher
  - Answer: {        
      authorId: UniqueEntityID
      exerciseId: UniqueEntityID
      content: string
      grade?: string
      createdAt: Date
      updatedAt?: Date
    }
- Exercise: {
      authorId: UniqueEntityID
      title: string
      content: string
      slug: Slug
      createdAt: Date
      updatedAt?: Date
    }
- Student: {
      name: string
    }
- Teacher: {
      name: string
    }
- Entity: {
      _id: UniqueEntityID
    }
- UniqueEntityID: {
      value: string (Random UUID)
    }
- Todas as entidades da aplicação herdam a entidade **Entity**, pois caso houver necessidade de trocar o ID das entidades (UUID, number, etc..) basta alterar em apenas um local


# Contextos: 
 - Tarefas/Exercícios

# Casos de Uso:
 - Professor tem acesso a criação de Atividades, assim podendo criar atividades para os alunos escolhidos.

 - Aluno consegue ver atividades designadas a ele, conseguindo responder as atividades.

 - Professor tem acesso as respostas dos alunos de cada atividade criada por ele.

 - Professor pode dar nota as respostas enviadas pelos alunos na atividade

## Comparações
### MVC ( Model View Controller )
- Separa aplicação em 3 pilares principais
- Focado em separar as principais responsabilidades da aplicação

### SOA ( Service Oriented Architecture )
- componentes são disponibilizados em forma de serviços
- Focado em deixar os componentes o mais independentes possíveis, podendo ser reutilizados e combinados

### Microservices Architecture ( Arquitetura de Micro serviços )
- estrutura a aplicação como um conjunto de pequenos serviços implantados de forma independente
- cada contexto vira um microservices, encapsulando um subdomínio específico

### Layered Architecture ( Arquitetura em Camadas )
- organiza a aplicação em camadas distintas, onde cada camada tem uma responsabilidade específica
- mais focada na separação de responsabilidade técnicas

### Event-Driven Architecture - EDA
- fluxos de controle são determinados por eventos e os componentes interagem entre si também por eventos
- consiste em eventos, produtores do evento, consumidores do evento e barramento de eventos (intermediário - transposta eventos dos produtores aos consumidores)

### Hexagonal Architecture - Arquitetura Hexagonal
- conhecida Ports and Adapters
- promove ideia da aplicação deve ser isolada de suas dependências externas
- núcleo (entidades/domínio) bem protegidos

# Clean Architecture
<img 
  src="https://blog.cleancoder.com/uncle-bob/images/2012-08-13-the-clean-architecture/CleanArchitecture.jpg" 
  alt="the-clean-architecture-diagram"
/>

- organização do código
- Desacoplamento
- SOLID 
  - Inversão de dependência -> permite que parte do código não dependa diretamente da implementação de uma outra camada do código, mas sim de uma abstração (de um contrato).
  - Ex: Camada de Casos de uso não deve depender da implementação da Camada de Infraestrutura.

