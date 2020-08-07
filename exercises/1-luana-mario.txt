import React from 'react';

const luana = {
  cliente: 'Luana',
  idade: 27,
  compras: [
    { nome: 'Notebook', preco: 'R$ 2500' },
    { nome: 'Geladeira', preco: 'R$ 3000' },
    { nome: 'Smartphone', preco: 'R$ 1500' },
  ],
  ativa: true,
};

const mario = {
  cliente: 'Mario',
  idade: 31,
  compras: [
    { nome: 'Notebook', preco: 'R$ 2500' },
    { nome: 'Geladeira', preco: 'R$ 3000' },
    { nome: 'Smartphone', preco: 'R$ 1500' },
    { nome: 'Guitarra', preco: 'R$ 3500' },
  ],
  ativa: false,
};

const App = () => {
  const dados = luana;
  const ativo = dados.ativa ? 'Ativa' : 'Inativa';

  const sum = dados.compras
    .map((obj) => Number(obj.preco.replace('R$ ', '')))
    .reduce((sumVal, curVal) => sumVal + curVal, 0);

  return (
    <div>
      <p>Nome: {dados.cliente}</p>
      <p>Idade: {dados.idade}</p>
      <p>
        Situação:{' '}
        <span style={dados.ativa ? { color: 'green' } : { color: 'red' }}>
          {ativo}
        </span>
      </p>
      <p>Total gasto: R$ {sum}</p>
      {sum > 10000 && <p>Você está gastando demais!</p>}
    </div>
  );
};

export default App;
