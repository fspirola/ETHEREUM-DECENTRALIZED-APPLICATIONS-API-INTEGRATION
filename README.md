# ETHEREUM-DECENTRALIZED-APPLICATIONS-API-INTEGRATION
Aula ETHEREUM DECENTRALIZED APPLICATIONS &amp; API INTEGRATION

Ethereum Decentralized Applications & API Integration
Profa. Solange Gueiros

Web3.js - Ethereum JavaScript API
https://web3js.readthedocs.io/
https://github.com/ethereum/web3.js/

Ethers.js - Complete Ethereum wallet implementation and utilities in JavaScript and TypeScript
https://docs.ethers.io/
https://github.com/ethers-io/ethers.js

Drizzle – Truffle - Redux library to connect a frontend to a blockchain
https://github.com/truffle-box/drizzle-box

Nethereum - Cross-platform Ethereum development framework with .NET
https://github.com/Nethereum/


Frontend Ethereum APIs
https://github.com/ConsenSys/ethereum-developer-tools-list#frontend-ethereum-apis

Front-End x Backend Interfaces
https://consensys.net/developers/#interfaces
https://ethereum.org/developers/#frontend-javascript-apis


Patterns & Best Practices

Open Zeppelin
https://github.com/OpenZeppelin/openzeppelin-contracts

Dapp tools – dappSys
http://dapp.tools/dappsys/

https://github.com/dapphub/dappsys

*************************************************
Para Rafael
*************************************************
CVM SandBox Regulatório
http://www.cvm.gov.br/noticias/arquivos/2019/20190828-1.html
http://www.cvm.gov.br/audiencias_publicas/ap_sdm/2019/sdm0519.html
http://www.cvm.gov.br/export/sites/cvm/audiencias_publicas/ap_sdm/anexos/2019/sdm0519_Edital.pdf
http://www.cvm.gov.br/export/sites/cvm/audiencias_publicas/ap_sdm/anexos/2019/sdm0519_aviso_de_prorrogacao.pdf
http://www.labinovacaofinanceira.com/wp-content/themes/enfold-child/pdf/Sand_box_lab_vs8_web.pdf

Noticias
http://www.cvm.gov.br/noticias/arquivos/2019/20190911-1.html
https://valor.globo.com/financas/noticia/2019/09/11/sandbox-regulatorio-amplia-efeito-disruptivo-diz-presidente-da-cvm.ghtml
https://cointimes.com.br/nova-regra-da-cvm-lanca-as-bases-para-adocao-de-modelo-de-sandbox-regulatorio-no-brasil/

*************************************************
Para Alexandre
*************************************************

https://rdai.money/
https://explorer.rdai.money/rDai/overview/
https://explorer.rdai.money/rDai/about
https://thegraph.com/explorer/subgraph/amxx/rdai
https://github.com/rtoken-project/rtoken-contracts
https://github.com/Amxx/rDai-explorer
https://github.com/Amxx/rDai-subgraph
https://github.com/Amxx?tab=repositories

*************************************************
Register
*************************************************

Diretorio base:
C:\ETH

Register
mkdir register

cd register

npm init -y

Abrir o visual code
code .

Open folder
C:\ETH\register

Criar o arquivo Register.sol



http://remix.ethereum.org/
Criar o arquivo Register.sol no remix também

Deploy and Run Transactions

Deploy

Interagir pelo remix para entender o que o smart contract faz

Remix - Solidity Compiler
Compilation details
Web3Deploy - copiar

Criar o arquivo register.js
colar
Nao vamos utilizar

Ganache install
https://www.npmjs.com/package/ganache-cli
npm install -g ganache-cli

Ganache Deploy
Em outro terminal
ganache-cli -i 10101 -e 1000 -l 8000000

No Remix, Deploy and Run Transactions
Environment: Web3Provider

register address no Ganache
Sol: 0xcD23ED53C52218fc41560eAc5aB2C468D405fb52

Paulo: 0x183E20C6DF3479bAc8E2ef6083292B1A296F4c9E
Luciano:0x453138E3551b8476a71c45D17818E8f0EFd68832
Adonai : 0xf3600584b379644E2e1712344B8c7197c0A58a2f
Wagner:0xeE161d374026B3b9e82d46C918d8896ebD247747
Renato:0x4fB80f88877732CbA877eF4dbEc895683D029e13
Rafael 0xd55D4C99B51C3B0B09025857c36019629E550BFc
Bia 0x2Da8D1C1458cDbf763D30506Cf9eDf2D05ce2042
Masson: 0x5Cd325D6c6b44c30a1EcA4316adf065E3E7A60b0
Leo: 0xBbD5702f551734b9cc5a6171560437b500BB875E
Sergio: 0x5d691db6884d6c2d8b8699d63cc5209fc3e76ab1
Itamar:  0x692a70d2e424a56d2c6c27aa97d1a86395877b3a

Servidor web local
npm install express --save

Criar o arquivo server.js

var express = require('express');
var app = express();
 
app.use(express.static(__dirname));
 
app.listen('3300');
console.log('http://localhost:3300/');


Em uma nova janela de terminal, 
no diretorio C:\ETH\register
executar
node server.js

No browser
http://localhost:3300

Interface Web
Criar o arquivo index.html

<!DOCTYPE html>
<html >
  <head>
    <title>Registro de informação no Blockchain</title>

    <!-- Bootstrap core CSS -->
    <link href='https://fonts.googleapis.com/css?family=Open+Sans:400,700' rel='stylesheet' type='text/css'>
    <link href='https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css' rel='stylesheet' type='text/css'>

    <script src="https://code.jquery.com/jquery-3.1.1.slim.min.js"></script>
    <script src="https://cdn.jsdelivr.net/gh/ethereum/web3.js@1.0.0-beta.37/dist/web3.min.js"></script>  
    
    <script src="./index.js"></script>    
  </head>

<body class="container-fluid">

    <h1 class="page-header">Registro de informação no Blockchain</h1>

    <div class="row">
        <div>
            <h3 class="sub-header">Gravar informação</h3>
            <form class="form-inline" role="form">
                <div class="form-group">
                    <table class="table" id="info-table">
                        <tr>
                            <td><label for="newInfo">Informação:</label> </td>
                            <td>
                                <input class="form-control" id="newInfo">
                            </td>                          
                        </tr>
                    </table>
                </div>
                <a href="#" onclick="newRegister()" class="btn btn-primary">Registrar</a>
            </form>
        </div>
    </div>    

    <div class="row">
        <div>
            <h3 class="sub-header">Verificar última informação registrada</h3>
            <form class="form-inline" role="form">
                <a href="#" onclick="loadRegister()" class="btn btn-primary">Verificar</a>
                <div class="form-group">
                    <table class="table" id="info-table">
                        <tr>
                            <td>Informação:</td>
                            <td>
                                <label id="lastInfo">
                            </td>                          
                        </tr>
                    </table>
                </div>                
            </form>
        </div>
    </div> 
 
  </body>
</html>


Criar o arquivo index.js


var web3 = new Web3(new Web3.providers.HttpProvider("http://localhost:8545"));

// Código para interagir com o contrato
var accounts; 
var account;

// Variáveis preenchidas a partir da publicação do contrato
var contractAddress = '0x47ae7e35ed0346d0d7ab0c4894e35acfcd724663';
var abi = JSON.parse( '[ { "inputs": [], "payable": false, "stateMutability": "nonpayable", "type": "constructor" }, { "constant": true, "inputs": [], "name": "getInfo", "outputs": [ { "internalType": "string", "name": "", "type": "string" } ], "payable": false, "stateMutability": "view", "type": "function" }, { "constant": true, "inputs": [], "name": "owner", "outputs": [ { "internalType": "address", "name": "", "type": "address" } ], "payable": false, "stateMutability": "view", "type": "function" }, { "constant": false, "inputs": [ { "internalType": "string", "name": "_info", "type": "string" } ], "name": "setInfo", "outputs": [], "payable": false, "stateMutability": "nonpayable", "type": "function" } ]' );


//baseContract = web3.eth.contract(abi);
//contract = baseContract.at(contractAddress);
contract = new web3.eth.Contract(abi, contractAddress);
console.log('Contract: ' + contract.address);
c
// Busca contas
web3.eth.getAccounts(function(err, accs) {
    if (err != null) {
        alert("Ocorreu um erro ao buscar suas contas.");
        return;
    }

    if (accs.length == 0) {
        alert("Nenhuma conta encontrada! Verifique se o Ethereum client está configurado corretamente.");
        return;
    }

    accounts = accs;
    account = accounts[0];
    console.log('Account: ' + account);
    web3.eth.defaultAccount = account;
});

function newRegister() {
    info = $("#newInfo").val();
    //alert (info);
    contract.methods.setInfo (info).send( {from: account}).then( function(tx) { 
        console.log( "Transaction: ", tx ); 
    });
    $("#newInfo").val('');
}

function loadRegister() {
    contract.methods.getInfo().call().then( function( info ) { 
        console.log( "info: ", info ) 
        //alert (info);
        document.getElementById('lastInfo').innerHTML = info;
    });
    
}


Atualizar 
contractAddress
abi

Remix - Compile
copy abi
https://www.textfixer.com/tools/remove-line-breaks.php

[ { "constant": false, "inputs": [ { "internalType": "string", "name": "_info", "type": "string" } ], "name": "setInfo", "outputs": [], "payable": false, "stateMutability": "nonpayable", "type": "function" }, { "inputs": [], "payable": false, "stateMutability": "nonpayable", "type": "constructor" }, { "constant": true, "inputs": [], "name": "getInfo", "outputs": [ { "internalType": "string", "name": "", "type": "string" } ], "payable": false, "stateMutability": "view", "type": "function" }, { "constant": true, "inputs": [], "name": "owner", "outputs": [ { "internalType": "address", "name": "", "type": "address" } ], "payable": false, "stateMutability": "view", "type": "function" } ]


F5 na janela do server
http://localhost:3300/

Botao direito - inspect - console


Publicando na testnet

Guarde seu mnemonic do Ganache!

Sol: debris discover still patch clarify robot chat project soldier victory other enemy
Luciano:  script use nerve topic leave fan bundle sauce awake eager bitter round
Adonai:  coil orient dish situate test slogan pen purse gas bullet loud cycle
Bia : actress gesture word butter panic voyage problem grab toilet hospital volume mosquito

Chamando o ganache com seu mnemonic, para utilizar as mesmas contas:
    
ganache-cli -i 10101 -e 1000 -l 8000000 -m "debris discover still patch clarify robot chat project soldier victory other enemy"

Configure o Metamask para utilizar seu mnemonic

Escolha a rede Ropsten

Botao Deposit - faucet


Transacao de publicacao do Register na Ropsten
Sol: https://ropsten.etherscan.io/tx/0x0431bea82659878f459a94d9eed68065b05128a0872a53b3aaf4c309277ee192

Paulo: https://ropsten.etherscan.io/tx/0xfc1520833a57648d0c8fb0bcce4f37f554f775b858adfd8bf85ede7eb0a71872

Renato: https://ropsten.etherscan.io/tx/0x2dcafbe3e88eedeafe6c80316629e083d3a7f5eea42f00157991c031834f0ce6
Fabio: https://ropsten.etherscan.io/tx/0xbd1ff70a3c69a90d4d824223f445f31b38236631689df955a9255a9b74ba8412 
Ulisses: https://ropsten.etherscan.io/tx/0xf2b67916157912662085a4d9245a495410012c88f704b95a9a52015ca4390afc
Adonai:https://ropsten.etherscan.io/tx/0xa3926709a85dbc335c7a0bd196ce541f574b9d319f26d07aff8b009eff2b50fa
Luciano:https://ropsten.etherscan.io/tx/0x08784e524db063d592b2fa24003610dcedaeb5e5ad65950da83c339b10286ea9
Sérgio : https://ropsten.etherscan.io/tx/0x8e3175848dc72ca9ba38f8736f07b70eaaace6cbcdb285f2671deabea4074413
Leo: https://ropsten.etherscan.io/tx/0x4efa049a895377250a9f167c46afa3f27058399e02c995efdd408f9665e195c7
Wagner: https://ropsten.etherscan.io/tx/0x01d9a386b516f1ebbf07ee64cfb61fa57f452feb774c88a033aa40994d87a369

Rafael:https://ropsten.etherscan.io/tx/0x7b58b163af8e48b403a1dc1b29008cb4cfb71ff3dcbc0828357306bc6ef91c17


Address Register na Ropsten
Sol: 0x804018bbFa4Ab1d89cc4A38B73BB213C4e8d3c3b
Renato:0x000a6722af989aC65720592993cCdBdd37d3C6d3
Luciano:0xb5AC0d8195D7139A2Dab7af04902749247F02330
Adonai : 0x53eA1A5b48e27cBCF7A451740e6D6D8E1EA17E4a
Fabio: 0xB74c2ea9c20DFb203C6E4B65B109d28111594342
Ulisses: 0x25c5651A68F5D1A5Ebd98eCb0Fdb562eB8167538
Paulo: 0x11E717c0EF8084d222ac7E8B014067e803fe2877
Sérgio : 0xb245dc244ad6f96790b3b576dca3854e5e452f3e
Leo: 0xbbd5702f551734b9cc5a6171560437b500bb875e
Bia: 0x5d038d84424c3F625f11145B88E7B73d58231503
Rafael: 0xD14B9b86aE364C499A45f812A69f6637828Be065
Masson: 0x4e99AeD6e5B4027CE8E1fab85DCD6aAb9F061204
Wagner:0x1BBB5C661dC7BC0C51A48Dfac28B8137c29D91B8

oneclickdapp
https://oneclickdapp.com/new/

Name: RegisterNome



Sol: https://oneclickdapp.com/forbid-watch/
Name:https://oneclickdapp.com/palma-avatar/ - Luciano
Name: RMST
Name:oneclickdapp.com/immune-plastic/ -Wagner

Ulisses: https://oneclickdapp.com/history-wizard/
Paulo: https://oneclickdapp.com/media-climax/
Fabio: https://oneclickdapp.com/brigade-clara/
Leo: https://oneclickdapp.com/courage-user/
Sergio : https://oneclickdapp.com/front-couple/
Renato:  https://oneclickdapp.com/winter-temple/
Masson: https://oneclickdapp.com/ceramic-vega/
Bia: https://oneclickdapp.com/tower-speed
Adonai : https://oneclickdapp.com/cola-alice/
Rafael: https://oneclickdapp.com/fiber-ferrari/

Exemplo Sol:
https://ropsten.etherscan.io/address/0x804018bbfa4ab1d89cc4a38b73bb213c4e8d3c3b

Publicando o código fonte do smart contract no EtherScan
Tab Contract
Verify and Publish

Single File
Compiler 0.5.16

Proxima tela
Copiar o codigo fonte do smart contract, a partir do Remix

Renato: https://ropsten.etherscan.io/address/0x000a6722af989ac65720592993ccdbdd37d3c6d3#readContract
Sérgio : https://ropsten.etherscan.io/address/0xb245dc244ad6f96790b3b576dca3854e5e452f3e#readContract

*********************************************
03/mar/2020
*********************************************

https://pad.riseup.net/p/fiapblock-2020-02

Para o grupo do Adonai, Luciano
http://www.myhealthmydata.eu/
https://www.bestperformancenews.com.br/healthchain-e-o-workshop-de-dados-da-h2oladuo/

************************************************

Ganache install
https://www.npmjs.com/package/ganache-cli
npm install -g ganache-cli

Ganache Execucao
Em outro terminal
ganache-cli -i 10101 -e 1000 -l 8000000


•DaoCanvas
•Ferramenta muito interessante utilizada para montar uma DAO
http://daocanvas.webflow.io/

Fotos do Canvas do EthDenver

Truffle install
npm i -g truffle

https://www.trufflesuite.com/boxes

Pet Shop
https://www.trufflesuite.com/boxes/pet-shop
https://www.trufflesuite.com/tutorials/pet-shop

Em C:\ETH
mkdir petshop
cd petshop
truffle unbox pet-shop

#no diretório contracts, criar o arquivo Adoption.sol

pragma solidity >=0.4.24;

contract Adoption {

    address[16] public adopters;

    // Adopting a pet
    function adopt(uint petId) public returns (uint) {
        require(petId >= 0 && petId <= 15);

        adopters[petId] = msg.sender;

        return petId;
    }

    // Retrieving the adopters
    function getAdopters() public view returns (address[16] memory) {
        return adopters;
    }
    
}

#Em migrations, criar 2_deploy_contracts.js

var Adoption = artifacts.require("Adoption");

module.exports = function(deployer) {
  deployer.deploy(Adoption);
};

#Trocar o conteudo do truffle-config.js

module.exports = {
  networks: {
    development: {
      host: "127.0.0.1",
      port: 8545,
      network_id: "*" // Match any network id
    }
  }
};

Em outro terminal, executar o ganache-cli
ganache-cli -i 10101 -e 1000 -l 8000000 -m "mnemonic"

Eduardo: ganache-cli -i 10101 -e 1000 -l 8000000 - m "estate claim dynamic vital furnace fold work produce debate cloud soap fog"

Renato: ganache-cli -i 10101 -e 1000 -l 8000000 -m "shell riot volume describe stereo spring dune plastic rocket private apple zone"

Sol:
ganache-cli -i 10101 -e 1000 -l 8000000 -m "debris discover still patch clarify robot chat project soldier victory other enemy"

Luciano: 
ganache-cli -i 10101 -e 1000 -l 8000000 - m "sadness mesh render void teach diamond inmate fault talent whip ostrich rent"
Adonai : ganache-cli -i 10101 -e 1000 -l 8000000 -m "solution diet apart retreat flock truth illegal energy evidence enforce torch grunt"
Paulo: ganache-cli -i 10101 -e 1000 -l 8000000 -m "actress gesture word butter panic voyage problem grab toilet hospital volume mosquito"


No 1o terminal
truffle migrate



Seed e Carteiras, accounts
https://programmingblockchain.gitbook.io/programmingblockchain/

https://programmingblockchain.gitbook.io/programmingblockchain/key_generation/new_key

https://iancoleman.io/bip39/


Configurar Metamask com a sua seed


Substituir src/js/App.js

App = {
  web3Provider: null,
  contracts: {},

  init: async function() {
    // Load pets.
    $.getJSON('../pets.json', function(data) {
      var petsRow = $('#petsRow');
      var petTemplate = $('#petTemplate');

      for (i = 0; i < data.length; i ++) {
        petTemplate.find('.panel-title').text(data[i].name);
        petTemplate.find('img').attr('src', data[i].picture);
        petTemplate.find('.pet-breed').text(data[i].breed);
        petTemplate.find('.pet-age').text(data[i].age);
        petTemplate.find('.pet-location').text(data[i].location);
        petTemplate.find('.btn-adopt').attr('data-id', data[i].id);

        petsRow.append(petTemplate.html());
      }
    });

    return await App.initWeb3();
  },

  initWeb3: async function() {
    // Modern dapp browsers...
  if (window.ethereum) {
    App.web3Provider = window.ethereum;
    try {
      // Request account access
      await window.ethereum.enable();
    } catch (error) {
      // User denied account access...
      console.error("User denied account access")
    }
}
// Legacy dapp browsers...
else if (window.web3) {
  App.web3Provider = window.web3.currentProvider;
}
// If no injected web3 instance is detected, fall back to Ganache
else {
  App.web3Provider = new Web3.providers.HttpProvider('http://localhost:7545');
}
web3 = new Web3(App.web3Provider);

    return App.initContract();
  },

  initContract: function() {
    $.getJSON('Adoption.json', function(data) {
      // Get the necessary contract artifact file and instantiate it with truffle-contract
      var AdoptionArtifact = data;
      App.contracts.Adoption = TruffleContract(AdoptionArtifact);
    
      // Set the provider for our contract
      App.contracts.Adoption.setProvider(App.web3Provider);
    
      // Use our contract to retrieve and mark the adopted pets
      return App.markAdopted();
    });

    return App.bindEvents();
  },

  bindEvents: function() {
    $(document).on('click', '.btn-adopt', App.handleAdopt);
  },

  markAdopted: function(adopters, account) {
    var adoptionInstance;

    App.contracts.Adoption.deployed().then(function(instance) {
      adoptionInstance = instance;

      return adoptionInstance.getAdopters.call();
    }).then(function(adopters) {
      for (i = 0; i < adopters.length; i++) {
        if (adopters[i] !== '0x0000000000000000000000000000000000000000') {
          $('.panel-pet').eq(i).find('button').text('Success').attr('disabled', true);
        }
      }
    }).catch(function(err) {
      console.log(err.message);
    });

  },

  handleAdopt: function(event) {
    event.preventDefault();

    var petId = parseInt($(event.target).data('id'));

    var adoptionInstance;

    web3.eth.getAccounts(function(error, accounts) {
      if (error) {
        console.log(error);
      }
    
      var account = accounts[0];
    
      App.contracts.Adoption.deployed().then(function(instance) {
        adoptionInstance = instance;
    
        // Execute adopt as a transaction by sending account
        return adoptionInstance.adopt(petId, {from: account});
      }).then(function(result) {
        return App.markAdopted();
      }).catch(function(err) {
        console.log(err.message);
      });
    });
  }

};

$(function() {
  $(window).load(function() {
    App.init();
  });
});


Executar no terminal:
npm run dev


Exercicio 1
Botao na interface web para fazer reset nas adoções
Implementar o que for necessário

1- Criar uma função no smart contract
2- Criar um botão no html
3- Fazer a chamada da função a partir do botão no App.js

Solucao
1- Criar uma função no smart contract

function release(uint petId) public returns (uint) {
//Devolve um cachorro
      require(petId >= 0 && petId <= 15);

      if (adopters[petId] == msg.sender) {
        adopters[petId] = address(0);
      }

      return petId;
    }

///
    function clearAdoption () public {
//Devolve todos os cachorros
        for (uint8 i = 0; i < 16 ; i++) {
            adopters[i] = address(0x0);
        }
    }
/// 


2- Criar um botão no html

    <div>
      <Button class="btn btn-default btn-Devolver" type="button" data-id="1">Devolver o Dog</Button>
    </div>
    

      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-push-2 text-center">
          <button class="btn btn-lg btn-danger btn-cancel" type="button" >Cancel All</button>
          <hr/>
          <br/>
        </div>
      </div>
      

3- Fazer a chamada da função a partir do botão no App.js


// bind do evento
  bindEvents: function() {
    $(document).on('click', '.btn-cancel', App.handleCancelAll);
  },

// funcao para cancelar
  handleCancelAll: function(event) {
    event.preventDefault();

    var adoptionInstance;

    web3.eth.getAccounts(function(error, accounts) {
      if (error) {
        console.log(error);
      }
    
      var account = accounts[0];
    
      App.contracts.Adoption.deployed().then(function(instance) {
        adoptionInstance = instance;
    
        // Execute adopt as a transaction by sending account
        return adoptionInstance.cancellAllAdoption({from: account});
      }).then(function(result) {
        $('.panel-pet button').text('Adopt').prop('disabled', false);
      }).catch(function(err) {
        console.log(err.message);
      });
    });
  }
};

petTemplate.find('.btn-reset').attr('data-reset', 121212);




Nova publicacao do smart contract
truffle migrate --reset


Codigo final

Adoption.sol
pragma solidity >=0.4.24;

contract Adoption {

    address[16] public adopters;

    // Adopting a pet
    function adopt(uint petId) public returns (uint) {
        require(petId >= 0 && petId <= 15);

        adopters[petId] = msg.sender;

        return petId;
    }

    // Retrieving the adopters
    function getAdopters() public view returns (address[16] memory) {
        return adopters;
    }

    function release(uint petId) public returns (uint) {
      require(petId >= 0 && petId <= 15);

      if (adopters[petId] == msg.sender) {
        adopters[petId] = address(0);
      }

      return petId;
    }

    function clearAdoption () public {
        for (uint8 i = 0; i < 16 ; i++) {
            adopters[i] = address(0x0);
        }
    }
    
}


index.html

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- The above 3 meta tags *must* come first in the head; any other head content must come *after* these tags -->
    <title>Pete's Pet Shop</title>

    <!-- Bootstrap -->
    <link href="css/bootstrap.min.css" rel="stylesheet">

    <!-- HTML5 shim and Respond.js for IE8 support of HTML5 elements and media queries -->
    <!-- WARNING: Respond.js doesn't work if you view the page via file:// -->
    <!--[if lt IE 9]>
      <script src="https://oss.maxcdn.com/html5shiv/3.7.3/html5shiv.min.js"></script>
      <script src="https://oss.maxcdn.com/respond/1.4.2/respond.min.js"></script>
    <![endif]-->
  </head>
  <body>
    <div class="container">
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-push-2">
          <h1 class="text-center">Pete's Pet Shop</h1>
          <hr/>
          <br/>
        </div>
      </div>

      <div>
        <button class="btn btn-lg btn-danger btn-cancel" type="button" >Cancel All</button>        
      </div>

      <div id="petsRow" class="row">
        <!-- PETS LOAD HERE -->
      </div>
    </div>

    <div id="petTemplate" style="display: none;">
      <div class="col-sm-6 col-md-4 col-lg-3">
        <div class="panel panel-default panel-pet">
          <div class="panel-heading">
            <h3 class="panel-title">Scrappy</h3>
          </div>
          <div class="panel-body">
            <img alt="140x140" data-src="holder.js/140x140" class="img-rounded img-center" style="width: 100%;" src="https://animalso.com/wp-content/uploads/2017/01/Golden-Retriever_6.jpg" data-holder-rendered="true">
            <br/><br/>
            <strong>Breed</strong>: <span class="pet-breed">Golden Retriever</span><br/>
            <strong>Age</strong>: <span class="pet-age">3</span><br/>
            <strong>Location</strong>: <span class="pet-location">Warren, MI</span><br/><br/>
            <button class="btn btn-default btn-adopt" type="button" data-id="0">Adopt</button>
          </div>
        </div>
      </div>
    </div>

    <!-- jQuery (necessary for Bootstrap's JavaScript plugins) -->
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>
    <!-- Include all compiled plugins (below), or include individual files as needed -->
    <script src="js/bootstrap.min.js"></script>
    <script src="js/web3.min.js"></script>
    <script src="js/truffle-contract.js"></script>
    <script src="js/app.js"></script>
  </body>
</html>


App.js

App = {
  web3Provider: null,
  contracts: {},

  init: async function() {
    // Load pets.
    $.getJSON('../pets.json', function(data) {
      var petsRow = $('#petsRow');
      var petTemplate = $('#petTemplate');

      for (i = 0; i < data.length; i ++) {
        petTemplate.find('.panel-title').text(data[i].name);
        petTemplate.find('img').attr('src', data[i].picture);
        petTemplate.find('.pet-breed').text(data[i].breed);
        petTemplate.find('.pet-age').text(data[i].age);
        petTemplate.find('.pet-location').text(data[i].location);
        petTemplate.find('.btn-adopt').attr('data-id', data[i].id);

        petsRow.append(petTemplate.html());
      }
    });

    return await App.initWeb3();
  },

  initWeb3: async function() {
    // Modern dapp browsers...
  if (window.ethereum) {
    App.web3Provider = window.ethereum;
    try {
      // Request account access
      await window.ethereum.enable();
    } catch (error) {
      // User denied account access...
      console.error("User denied account access")
    }
}
// Legacy dapp browsers...
else if (window.web3) {
  App.web3Provider = window.web3.currentProvider;
}
// If no injected web3 instance is detected, fall back to Ganache
else {
  App.web3Provider = new Web3.providers.HttpProvider('http://localhost:7545');
}
web3 = new Web3(App.web3Provider);

    return App.initContract();
  },

  initContract: function() {
    $.getJSON('Adoption.json', function(data) {
      // Get the necessary contract artifact file and instantiate it with truffle-contract
      var AdoptionArtifact = data;
      App.contracts.Adoption = TruffleContract(AdoptionArtifact);
    
      // Set the provider for our contract
      App.contracts.Adoption.setProvider(App.web3Provider);
    
      // Use our contract to retrieve and mark the adopted pets
      return App.markAdopted();
    });

    return App.bindEvents();
  },

  bindEvents: function() {
    $(document).on('click', '.btn-adopt', App.handleAdopt);
    $(document).on('click', '.btn-cancel', App.handleCancelAll);
  },

  markAdopted: function(adopters, account) {
    var adoptionInstance;

    App.contracts.Adoption.deployed().then(function(instance) {
      adoptionInstance = instance;

      return adoptionInstance.getAdopters.call();
    }).then(function(adopters) {
      for (i = 0; i < adopters.length; i++) {
        if (adopters[i] !== '0x0000000000000000000000000000000000000000') {
          $('.panel-pet').eq(i).find('button').text('Success').attr('disabled', true);
        }
      }
    }).catch(function(err) {
      console.log(err.message);
    });

  },

  handleAdopt: function(event) {
    event.preventDefault();

    var petId = parseInt($(event.target).data('id'));

    var adoptionInstance;

    web3.eth.getAccounts(function(error, accounts) {
      if (error) {
        console.log(error);
      }
    
      var account = accounts[0];
    
      App.contracts.Adoption.deployed().then(function(instance) {
        adoptionInstance = instance;
    
        // Execute adopt as a transaction by sending account
        return adoptionInstance.adopt(petId, {from: account});
      }).then(function(result) {
        return App.markAdopted();
      }).catch(function(err) {
        console.log(err.message);
      });
    });
  },

// funcao para cancelar
handleCancelAll: function(event) {
  event.preventDefault();

  var adoptionInstance;

  web3.eth.getAccounts(function(error, accounts) {
    if (error) {
      console.log(error);
    }
  
    var account = accounts[0];
  
    App.contracts.Adoption.deployed().then(function(instance) {
      adoptionInstance = instance;
  
      // Execute adopt as a transaction by sending account
      return adoptionInstance.clearAdoption({from: account});
    }).then(function(result) {
      $('.panel-pet button').text('Adopt').prop('disabled', false);
    }).catch(function(err) {
      console.log(err.message);
    });
    });
  }
};  


$(function() {
  $(window).load(function() {
    App.init();
  });
});


Drizzle

https://www.trufflesuite.com/boxes/drizzle

C:\ETH
mkdir drizzle
cd drizzle
truffle unbox drizzle

Substituir truffle-config.js

const path = require("path");

module.exports = {

  contracts_build_directory: path.join(__dirname, "app/src/contracts"),
  networks: {
    development: {
      host: "127.0.0.1",
      port: 8545,
      network_id: "*" // Match any network id
    }

  }
};


truffle migrate

cd app
npm run start


*********************************************
05/mar/2020
*********************************************

Truffle install
npm install -g truffle

Ganache install
https://www.npmjs.com/package/ganache-cli
npm install -g ganache-cli

Metamask
instalar extensão no chrome

Executar o ganache com seu mnemonic, para utilizar as mesmas contas:
Sol:
ganache-cli -i 10101 -e 1000 -l 8000000 -m "debris discover still patch clarify robot chat project soldier victory other enemy"

Renato:
ganache-cli -i 10101 -e 1000 -l 8000000 -m "shell riot volume describe stereo spring dune plastic rocket private apple zone"

Github

No terminal, em C:\
git clone https://github.com/solangegueiros/dapp-register.git register

cd register

Abrir no Visual Code
code .

cd register-web3basic
npm i

publicar pelo remix
atualizar o contractAddress

node server.js
http://localhost:3300/

cd register-truffle
npm i

truffle migrate

npm run dev

Erros de payload no Metamask
Settings -> Advanced -> Reset account

Em register-web3basic
index.js
Atualizar o address do Register
var contractAddress = '0x6f5Ea1DE178A611083F260F6F88Df88CB2B933B8';

Com o que foi publicado pelo truffle


Em outro terminal
cd C:\register\register-web3basic

node server.js
http://localhost:3300/


cd ..
Em C:\register\
mkdir register-react

cd register-react

truffle init
npm init -y

Copiar de C:\register\register-truffle
contracts
migrations

Atualizar o truffle-config.js

 

const path = require("path");

module.exports = {  
  contracts_build_directory: path.join(__dirname, "app/src/contracts"), 
  networks: {
    development: {
      host: "127.0.0.1",
      port: 8545,
      network_id: "*"
    }
  },
  compilers: {
    solc: {
      version: "0.5.2",
    }
  }
 }

Em C:\register\register-react

npx create-react-app app

Se nao tiver o npx:
npm install -g npx

truffle migrate

cd app
npm start

Substituir App.js
import React, { Component } from 'react';
import Web3 from 'web3'
import './App.css';
import Register from "./contracts/Register.json";

class App extends Component {

  constructor(props) {
    super(props)
    this.state = {
      account: '',
      contract: null,
      info: ''
    }
  }

  async componentWillMount() {
    await this.loadWeb3()
    await this.loadBlockchainData()
  }

  async loadWeb3() {
    if (window.ethereum) {
      window.web3 = new Web3(window.ethereum)
      await window.ethereum.enable()
    }
    else if (window.web3) {
      window.web3 = new Web3(window.web3.currentProvider)
    }
    else {
      window.alert('Non-Ethereum browser detected. You should consider trying MetaMask!')
    }
    console.log (window.web3.currentProvider)
  }

  async loadBlockchainData() {
    const web3 = window.web3
    // Load account
    const accounts = await web3.eth.getAccounts()
    console.log ('account: ', accounts[0])
    this.setState({ account: accounts[0] })
  
    //Verifica qual rede está ativa no web3    
    const networkId = await web3.eth.net.getId()
    console.log ('networkId: ', networkId)
    //Verifica se o smart contract foi publicado nessa rede
    const networkData = Register.networks[networkId]
    console.log ('networkData: ', networkData)
    if(networkData) {
      const abi = Register.abi
      const address = networkData.address
      console.log ('contract address: ', address)
      const contract = new web3.eth.Contract(abi, address)
      console.log ('contract: ', contract)
      this.setState({ contract })
      const info = await contract.methods.getInfo().call()
      console.log ('info: ', info)
      this.setState({ info })
    } else {
      window.alert('Smart contract not deployed to detected network.')
    }
  }

  setInfo = (newInfo) => {
    console.log ('newInfo: ', newInfo)
    this.state.contract.methods.setInfo(newInfo).send({ from: this.state.account })
    .once('receipt', (receipt) => {
      console.log ('transaction receipt: ', receipt)
      this.setState({ info: newInfo })
    })
  }  

  render() {
    return (
      <div>
        <div className="row text-center">
          <h1>Register using React</h1>
          <p> Informação: { this.state.info } </p>
          <hr/>            
          <br/>
        </div>
        <div className="row">
          <form onSubmit={(event) => {
            event.preventDefault()
            //const newInfo = this.newInfo.value
            const newInfo = this.input.value
            this.setInfo(newInfo)
          }}>
            <input
              type='text'
              className='form-control mb-1'
              ref={(input) => { this.input = input }}
            />
            <input
              type='submit'
              className='btn btn-block btn-primary'
              value='Set'
            />            
          </form>
        </div>
      </div>
      );
    }        
}

export default App;


Em outro terminal
Em C:\register\register-react\app
cd C:\register\register-react\app
npm install -e web3 


C:\register\register-react\app\src\index.js

import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';
import * as serviceWorker from './serviceWorker';

ReactDOM.render(<App />, document.getElementById('root'));

// If you want your app to work offline and load faster, you can change
// unregister() to register() below. Note this comes with some pitfalls.
// Learn more about service workers: https://bit.ly/CRA-PWA
serviceWorker.unregister();


serviceWorker.js
// This optional code is used to register a service worker.
// register() is not called by default.

// This lets the app load faster on subsequent visits in production, and gives
// it offline capabilities. However, it also means that developers (and users)
// will only see deployed updates on subsequent visits to a page, after all the
// existing tabs open on the page have been closed, since previously cached
// resources are updated in the background.

// To learn more about the benefits of this model and instructions on how to
// opt-in, read https://bit.ly/CRA-PWA

const isLocalhost = Boolean(
  window.location.hostname === 'localhost' ||
    // [::1] is the IPv6 localhost address.
    window.location.hostname === '[::1]' ||
    // 127.0.0.0/8 are considered localhost for IPv4.
    window.location.hostname.match(
      /^127(?:\.(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)){3}$/
    )
);

export function register(config) {
  if (process.env.NODE_ENV === 'production' && 'serviceWorker' in navigator) {
    // The URL constructor is available in all browsers that support SW.
    const publicUrl = new URL(process.env.PUBLIC_URL, window.location.href);
    if (publicUrl.origin !== window.location.origin) {
      // Our service worker won't work if PUBLIC_URL is on a different origin
      // from what our page is served on. This might happen if a CDN is used to
      // serve assets; see https://github.com/facebook/create-react-app/issues/2374
      return;
    }

    window.addEventListener('load', () => {
      const swUrl = `${process.env.PUBLIC_URL}/service-worker.js`;

      if (isLocalhost) {
        // This is running on localhost. Let's check if a service worker still exists or not.
        checkValidServiceWorker(swUrl, config);

        // Add some additional logging to localhost, pointing developers to the
        // service worker/PWA documentation.
        navigator.serviceWorker.ready.then(() => {
          console.log(
            'This web app is being served cache-first by a service ' +
              'worker. To learn more, visit https://bit.ly/CRA-PWA'
          );
        });
      } else {
        // Is not localhost. Just register service worker
        registerValidSW(swUrl, config);
      }
    });
  }
}

function registerValidSW(swUrl, config) {
  navigator.serviceWorker
    .register(swUrl)
    .then(registration => {
      registration.onupdatefound = () => {
        const installingWorker = registration.installing;
        if (installingWorker == null) {
          return;
        }
        installingWorker.onstatechange = () => {
          if (installingWorker.state === 'installed') {
            if (navigator.serviceWorker.controller) {
              // At this point, the updated precached content has been fetched,
              // but the previous service worker will still serve the older
              // content until all client tabs are closed.
              console.log(
                'New content is available and will be used when all ' +
                  'tabs for this page are closed. See https://bit.ly/CRA-PWA.'
              );

              // Execute callback
              if (config && config.onUpdate) {
                config.onUpdate(registration);
              }
            } else {
              // At this point, everything has been precached.
              // It's the perfect time to display a
              // "Content is cached for offline use." message.
              console.log('Content is cached for offline use.');

              // Execute callback
              if (config && config.onSuccess) {
                config.onSuccess(registration);
              }
            }
          }
        };
      };
    })
    .catch(error => {
      console.error('Error during service worker registration:', error);
    });
}

function checkValidServiceWorker(swUrl, config) {
  // Check if the service worker can be found. If it can't reload the page.
  fetch(swUrl, {
    headers: { 'Service-Worker': 'script' }
  })
    .then(response => {
      // Ensure service worker exists, and that we really are getting a JS file.
      const contentType = response.headers.get('content-type');
      if (
        response.status === 404 ||
        (contentType != null && contentType.indexOf('javascript') === -1)
      ) {
        // No service worker found. Probably a different app. Reload the page.
        navigator.serviceWorker.ready.then(registration => {
          registration.unregister().then(() => {
            window.location.reload();
          });
        });
      } else {
        // Service worker found. Proceed as normal.
        registerValidSW(swUrl, config);
      }
    })
    .catch(() => {
      console.log(
        'No internet connection found. App is running in offline mode.'
      );
    });
}

export function unregister() {
  if ('serviceWorker' in navigator) {
    navigator.serviceWorker.ready
      .then(registration => {
        registration.unregister();
      })
      .catch(error => {
        console.error(error.message);
      });
  }
}

Em C:\register\
cd C:\register\
mkdir register-drizzle
cd register-drizzle

truffle init
npm init -y

Copiar de C:\register\register-react
contracts
migrations
truffle-config.js
 
Em C:\register\register-drizzle

npx create-react-app app

truffle migrate

cd app
# by adonai
npm install -g npm
git config --global url."https://".insteadOf git://

# by wagner
npm install websocket 
npm install drizzle --save


npm start
------------------------------------------------------------------------------------------------
------------------------------------------------------------------------------------------------

index.js
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
import * as serviceWorker from './serviceWorker';

// import drizzle functions and contract artifact
import { Drizzle } from "drizzle";
import Register from "./contracts/Register.json";

// let drizzle know what contracts we want and how to access our test blockchain
const options = {
  contracts: [Register],
};

// setup the drizzle store and drizzle
const drizzle = new Drizzle(options);

ReactDOM.render(<App drizzle={drizzle} />, document.getElementById('root'));

// If you want your app to work offline and load faster, you can change
// unregister() to register() below. Note this comes with some pitfalls.
// Learn more about service workers: https://bit.ly/CRA-PWA
serviceWorker.unregister();

App.js
import React, { Component } from "react";
import './App.css';
import GetInfo from "./components/GetInfo";
import SetInfo from "./components/SetInfo";

class App extends Component {
  state = { loading: true, drizzleState: null };

  componentDidMount() {
    const { drizzle } = this.props;

    // subscribe to changes in the store
    this.unsubscribe = drizzle.store.subscribe(() => {

      // every time the store updates, grab the state from drizzle
      const drizzleState = drizzle.store.getState();

      // check to see if it's ready, if so, update local component state
      if (drizzleState.drizzleStatus.initialized) {
        this.setState({ loading: false, drizzleState });
      }
    });
  }

  componentWillUnmount() {
    this.unsubscribe();
  }

  render() {
    if (this.state.loading) return "Loading Drizzle...";
    return (
      <div className="App">
        <h1>Register</h1>
        <GetInfo
          drizzle={this.props.drizzle}
          drizzleState={this.state.drizzleState}
        />
        <SetInfo
          drizzle={this.props.drizzle}
          drizzleState={this.state.drizzleState}
        />        
      </div>
    );
  }
}

export default App;


em C:\register\register-drizzle\app\src\components

criar GetInfo.js

import React from "react";

class GetInfo extends React.Component {
  state = { dataKey: null };

  async componentDidMount() {
    const { drizzle, drizzleState } = this.props;

    await window.ethereum.enable();

    console.log(drizzle);
    console.log(drizzleState);

    const contract = drizzle.contracts.Register;
    // let drizzle know we want to watch the `myString` method
    const dataKey = contract.methods["getInfo"].cacheCall();
    // save the `dataKey` to local component state for later reference
    this.setState({ dataKey });    
  }

  render() {
    // get the contract state from drizzleState
    const { Register } = this.props.drizzleState.contracts;

    // using the saved `dataKey`, get the variable we're interested in
    const info = Register.getInfo[this.state.dataKey];

    // if it exists, then we display its value
    return (
      <div>
        <h2>GetInfo Component</h2>
        <p>Info: {info && info.value}</p>
      </div>
    );
  }
}

export default GetInfo;



criar SetInfo.js

import React from "react";

class SetInfo extends React.Component {
  state = { stackId: null, inputValue: "" };

  handleInputChange = e => this.setState({ inputValue: e.target.value });

  setValue = value => {
    const { drizzle, drizzleState } = this.props;
    const contract = drizzle.contracts.Register;

    // let drizzle know we want to call the `set` method with `value`
    const stackId = contract.methods["setInfo"].cacheSend(this.state.inputValue, {
      from: drizzleState.accounts[0]
    });

    // save the `stackId` for later reference
    this.setState({ stackId });
  };

  getTxStatus = () => {
    const { stackId } = this.state;
    // get the transaction states from the drizzle state
    const { transactions, transactionStack } = this.props.drizzleState;

    // get the transaction hash using our saved `stackId`
    const txHash = transactionStack[stackId];

    // if transaction hash does not exist, don't display anything
    if (!txHash) return null;

    //console.log(txHash);
    //console.log(transactions[txHash]);
    if (transactions[txHash] != null) 
      if (transactions[txHash].receipt != null) 
        console.log('receipt \n', transactions[txHash].receipt);

    // otherwise, return the transaction status
    return `Transaction status: ${transactions[txHash] && transactions[txHash].status}`;
  };

  render() {
    return (
      <div>
        <h2>SetInfo Component</h2>
        <input
          type="text"
          value={this.state.inputValue}
          onChange={this.handleInputChange}
        />
        <button onClick={this.setValue}>Set Info</button>
        <div>{this.getTxStatus()}</div>
      </div>
    );
  }
}

export default SetInfo;



*******************************************
10/mar/2020
*******************************************

npm install ganache-cli, truffle, metamask


Truffle install
npm install -g truffle

Ganache install
npm install -g ganache-cli

Metamask
instalar extensão no chrome


Executar ganache-cli com seu mnemonic

Instalar metamask
Abrir o metamask com seu mnemonic

SOL:
ganache-cli -i 10101 -e 1000 -l 8000000 -m "debris discover still patch clarify robot chat project soldier victory other enemy"
Paulo: ganache-cli -i 10101 -e 1000 -l 8000000 -m "actress gesture word butter panic voyage problem grab toilet hospital volume mosquito"

Em C:
git clone https://github.com/solangegueiros/dapp-register.git register

cd register

******************************************
drizzle-react

cd register-drizzle-react
Abrir o visual code
code .

cd app 
npm install

Em outro terminal 2
cd C:\register\register-drizzle-react
truffle migrate --reset

No terminal 1 (do app)
npm start

CTRL + C

******************************************
drizzle-react-components

cd C:\register\register-drizzle-react-components
truffle migrate --reset

cd app
npm install
npm start

CTRL + C

******************************************
drizzle-event

cd C:\register\register-drizzle-event
truffle migrate --reset

cd app
npm install
npm start

**********************************
Links interessantes:
POA
https://www.poa.network/


USO DA BLOCKCHAIN DO ETHEREUM PARA A REALIZAÇÃO DE LEILÕES DE ENERGIA ELÉTRICA ATRAVÉS DA CRIAÇÃO DE FERRAMENTA WEB
http://repositorio.ufc.br/bitstream/riufc/49959/3/2019_tcc_scsousa.pdf

**********************************
register-ethersJs

cd C:\register\register-ethersJs

Remix
http://remix.ethereum.org/

Criar register.sol
Copiar do local C:\register\register-ethersJs\register.sol
e colar no remix

DEPLOY & RUN TRANSACTIONS
Network web3Provider

deploy 

copiar o address

Sol: 0xeBA0860B112150ADF34e5e0D14BF2931448A7373
Alexandre : 0x35850Afcb4c08ce98BD24AD87C6054Aff1Dd924C

Colar em index.js

npm install

node server.js

http://localhost:3300/

Para usar com o metamask
Comentar a linha 1 do index.js
Acrescentar na linha 2
provider = new ethers.providers.Web3Provider(web3.currentProvider);

**********************************
Token

https://www.trufflesuite.com/boxes/tutorialtoken
https://www.trufflesuite.com/tutorials/robust-smart-contracts-with-openzeppelin
https://github.com/truffle-box/tutorialtoken-box/tree/develop

em C:\ETH
cd C:\ETH
criar se nao existir C:\ETH

mkdir token
cd token

truffle unbox tutorialtoken

ren truffle.js truffle-config.js

del node_modules /Q
del package-lock.json
npm install


https://www.npmjs.com/package/@openzeppelin/contracts
npm install -e @openzeppelin/contracts

Abrir no visual code
code .

Arquivo truffle-config.js
module.exports = {
 networks: {
   development: {
     host: "127.0.0.1",
     port: 8545,
     network_id: "*"
   }
 },
 compilers: {
   solc: {
     version: "0.5.2",
   }
 }
}

Migrations.sol
diretorio contracts, arquivo Migrations.sol

pragma solidity >=0.4.21 <0.7.0;
 
contract Migrations {
 address public owner;
 uint public last_completed_migration;
 
 modifier restricted() {
   if (msg.sender == owner) _;
 }
 
 constructor() public {
   owner = msg.sender;
 }
 
 function setCompleted(uint completed) public restricted {
   last_completed_migration = completed;
 }
}

Token.sol
diretorio contracts, criar arquivo Token.sol

pragma solidity 0.5.2;
 
import '@openzeppelin/contracts/token/ERC20/ERC20.sol';
 
contract Token is ERC20 {
   string public name = "Sol token";
   string public symbol = "SOLT";
   uint8 public decimals = 2;
   uint public INITIAL_SUPPLY = 150000;
 
   constructor() public {
       _mint(msg.sender, INITIAL_SUPPLY);
   }
}


diretorio migrations, arquivo 2_deploy_contracts.js

var Token = artifacts.require("Token");
 
module.exports = function(deployer) {
 deployer.deploy(Token);
};

No terminal
truffle migrate


src/js/app.js
Substituir src/js/app.js

App = {
  web3Provider: null,
  contracts: {},
  
  init: function() {
    return App.initWeb3();
  },
  
  initWeb3: async function() {
    // Modern dapp browsers...
    if (window.ethereum) {
      App.web3Provider = window.ethereum;
      try {
        // Request account access
        await window.ethereum.enable();
      } catch (error) {
        // User denied account access...
        console.error("User denied account access")
      }
    }
    // Legacy dapp browsers...
    else if (window.web3) {
      App.web3Provider = window.web3.currentProvider;
    }
    // If no injected web3 instance is detected, fall back to Ganache
    else {
      App.web3Provider = new Web3.providers.HttpProvider('http://localhost:8545');
    }
    web3 = new Web3(App.web3Provider);
  
    return App.initContract();
  },
  
  initContract: function() {
    $.getJSON('Token.json', function(data) {
      // Get the necessary contract artifact file and instantiate it with truffle-contract.
      var TokenArtifact = data;
      App.contracts.Token = TruffleContract(TokenArtifact);
  
      // Set the provider for our contract.
      App.contracts.Token.setProvider(App.web3Provider);
  
      App.getSymbol();
      return App.getBalances();
    });
  
    return App.bindEvents();
  },
  
  bindEvents: function() {
    $(document).on('click', '#transferButton', App.handleTransfer);
  },
  
  handleTransfer: function(event) {
    event.preventDefault();
  
    var amount = parseInt($('#TokenTransferAmount').val());
    var toAddress = $('#TokenTransferAddress').val();
  
    console.log('Transfer ' + amount + ' tokens to ' + toAddress);
    var tokenInstance;
  
    web3.eth.getAccounts(function(error, accounts) {
      if (error) {
        console.log(error);
      }
      var account = accounts[0];
  
      App.contracts.Token.deployed().then(function(instance) {
        tokenInstance = instance;
        return tokenInstance.transfer(toAddress, amount, {from: account, gas: 100000});
      }).then(function(result) {
        alert('Transfer Successful!');
        return App.getBalances();
      }).catch(function(err) {
        console.log(err.message);
      });
    });
  },
  
  getSymbol: function() {
    console.log('Getting symbol...'); 
    var tokenInstance;
     web3.eth.getAccounts(function(error, accounts) {
      if (error) {
        console.log(error);
      } 
      var account = accounts[0];
       App.contracts.Token.deployed().then(function(instance) {
        tokenInstance = instance; 
        return tokenInstance.symbol();
      }).then(function(result) {
        $('#TokenSymbol').text(result);
      }).catch(function(err) {
        console.log(err.message);
      });
    });
  },
  getBalances: function() {
    console.log('Getting balances...');
    var tokenInstance;
  
    web3.eth.getAccounts(function(error, accounts) {
      if (error) {
        console.log(error);
      }
      var account = accounts[0];
  
      App.contracts.Token.deployed().then(function(instance) {
        tokenInstance = instance;
        return tokenInstance.balanceOf(account);
      }).then(function(result) {
        balance = result.c[0];
  
        $('#TokenBalance').text(balance);
      }).catch(function(err) {
        console.log(err.message);
      });
    });
  }
  
 };
  
 $(function() {
  $(window).load(function() {
    App.init();
  });
 });
 


src/index.html
Substituir src/index.html

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- The above 3 meta tags *must* come first in the head; any other head content must come *after* these tags -->
    <title>Token - Wallet</title>

    <!-- Bootstrap -->
    <link href="css/bootstrap.min.css" rel="stylesheet">

    <!-- HTML5 shim and Respond.js for IE8 support of HTML5 elements and media queries -->
    <!-- WARNING: Respond.js doesn't work if you view the page via file:// -->
    <!--[if lt IE 9]>
      <script src="https://oss.maxcdn.com/html5shiv/3.7.3/html5shiv.min.js"></script>
      <script src="https://oss.maxcdn.com/respond/1.4.2/respond.min.js"></script>
    <![endif]-->
  </head>
  <body>
    <div class="container">
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-push-2">
          <h1 class="text-center">Token Wallet</h1>
          <hr/>
          <br/>
        </div>
      </div>

      <div id="petsRow" class="row">
        <div class="col-sm-6 col-sm-push-3 col-md-4 col-md-push-4">
          <div class="panel panel-default">
            <div class="panel-heading">
              <h3 class="panel-title">My Wallet</h3>
            </div>
            <div class="panel-body">
              <h4>Balance</h4>
              <strong>Balance</strong>: <span id="TokenBalance"></span> <span id="TokenSymbol"></span><br/><br/>
              <h4>Transfer</h4>
              <input type="text" class="form-control" id="TokenTransferAddress" placeholder="Address" />
              <input type="text" class="form-control" id="TokenTransferAmount" placeholder="Amount" />
              <button class="btn btn-primary" id="transferButton" type="button">Transfer</button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- jQuery (necessary for Bootstrap's JavaScript plugins) -->
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>
    <!-- Include all compiled plugins (below), or include individual files as needed -->
    <script src="js/bootstrap.min.js"></script>
    <script src="js/web3.min.js"></script>
    <script src="js/truffle-contract.js"></script>
    <script src="js/app.js"></script>
  </body>
</html>


npm install

Executar o frontend
npm run dev



Remix - Publicar na Ropsten

Truffle Flattener
Truffle Flattener concats solidity files developed under Truffle with all of their dependencies

npm install truffle-flattener 

Windows:
.\node_modules\.bin\truffle-flattener ./contracts/Token.sol > .\contracts\Token-flat.sol

Linux
./node_modules/.bin/truffle-flattener ./contracts/Token.sol > ./contracts/Token-flat.sol


Remix

Criar Token.sol
Colar conteudo de Token-flat.sol

Metamask 
escolher rede Ropsten

No Remix alterar a versão do compilador para 0.5.2
Alterar a versão do compilador para 0.5.2

Em DEPLOY & RUN TRANSACTIONS
Environment
InjectedWeb3

Escolher 
Token - browser/Token.sol

Deploy

Transacoes

Sol: 
https://ropsten.etherscan.io/tx/0x29d72ec67eef344a7dce30be5556d360b7175853b107939b5328b42716f9fa4a

Sergio : 
https://ropsten.etherscan.io/tx/0x4093d3d35d68d4bd47af035e7f3f31f41029a8a57fb551ee00480a4405d8d9cf   

Ulisses:
https://ropsten.etherscan.io/tx/0x3dac9fba051391c790769c49e951efc13737d3aa6529411665edf7fc3602ccf2 

GNETO 
https://ropsten.etherscan.io/tx/0x51f769139fdc9eb3c818b35f17c0cc5485b5bad5d26dc1f34251a999ad004cc9
contract 0xae9fd97e9ae0113299f2831e60e4aec3a7f5b281
GNETO account  0xa2F57C06997A5AC6B5E0e3176E18178fC098112c 

Paulo
https://ropsten.etherscan.io/tx/0xefe792aba88239c0403285ee4cd7b78ab2f1053d5fa4367d99cbd8ab6528685a

Wagner
https://ropsten.etherscan.io/tx/0x4c3feae65f156870cb682a728b09115c018c29315414b0342db64a33260ba3dc

Fabio
https://ropsten.etherscan.io/tx/0xda53395276c9b16f6959909da9b46e41c35edcf4351f3500e2d0685d59281d78

Alexandre
https://ropsten.etherscan.io/tx/0x7ffb9c3cf2d0cd612ae2eea360cd6bc043a252e9f591599b9c1ab81bee9758c7

Rafael
https://ropsten.etherscan.io/tx/0x59f9e7af1f957afb058642249ab0e212f9245aa47c88daf18289821793b6d72e

Adonai
https://ropsten.etherscan.io/tx/0x4f1dff3fd94a6ed599e1e0fbfd2b69569288a08fa34c989e0f9f54243f520458

Masson
https://ropsten.etherscan.io/tx/0xd2120da6b5a54561c4e84751a8a60d078709736fd62a1a989639851a84679827

Endereco do Token
Sol - FiapT
0x6368571dC7F34438e484D6C1aA2A407c347bec29
ULISSES - FLS
0x82c38FC3e330d5D24FF8B9B5582A13EB7C197879
Paulo - MTN
0x323dc1454ab6d951215c9c965fae99142e363b73
Wagner
0xAaEDF2615BE64d6108d594B56549Bcf844E8416e
Sergio : SKYT
0x3B462f890FC4290A0D385dc49cfBf06Db76FbACb
Alexandre:
0x04b191763126D46DCb58d7A44A92c8dEed5F5256
Fabio:
0x0F63bCFD952858A110E683fb09db6BCfBbfFe2B5
Luciano:
0xA9380100a76FAdcDAf3528E05CA3a19D82Ef8FE5
Rafael
0xb0b5da55f3e328f34d43ecaefc946e6388c31d8c
Adonai - AMMT
0x149faebf02909bd956ec756a841f0cd7b060cba5
Masson
0x35c613a9c1cd56930bfa9fd4b8683ee93df3b6e9

guineitor
https://ropsten.etherscan.io/tx/0x51f769139fdc9eb3c818b35f17c0cc5485b5bad5d26dc1f34251a999ad004cc9
contract 0xae9fd97e9ae0113299f2831e60e4aec3a7f5b281
GNETO account  0xa2F57C06997A5AC6B5E0e3176E18178fC098112c 



Publicando o código fonte do smart contract no EtherScan
Tab Contract
Verify and Publish

Single File
Compiler 0.5.16

Proxima tela
Copiar o codigo fonte do smart contract, a partir do Remix


Metamask
Adicionar o token
Menu
Add Token
Copiar o endereço do token


Enderecos das carteiras do Metamask
Sol
0x27E2c17fdFe778eC84BC093Ef81231deD50deCe7
ULISSES
0x25c5651A68F5D1A5Ebd98eCb0Fdb562eB8167538
Rafael
0x2438cF70db79f32400a327DE70Bdea0e0C593d23
Paulo
0x1a65E13DD40d116C8d658dF30D071a36A1195396
Fabio FABT
0xbc264238A05aDdcAEabAF281da49D45Ff30ac172
Sergio
0xCDC8c4728F01987B414741fC46930e0Ec1eae72b
Eduardo
0x645Bfb543Ec6E06F227Ea355751B528f26dA5e03
Masson
0x3f57d5886ae0af954206756a3c2b9a92a4dd419e

build/contracts/Token.json
Atualizar build/contracts/Token.json
Copiar a rede local 10101 e alterar para 3
Alterar address e transactionHash

   "3": {
     "events": {...},
     "links": {},
     "address": "0x1D7cb96172D33991134Ce029bB0e6598100ee3CB",
     "transactionHash": "0xd0fbf44ca10ae72a909d442618a32948a0911761cfc14fe2f26c5c160c98636b"
   },
