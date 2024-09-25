# HeaderADM

import React, { useState } from 'react';
import "../css/HeaderUser.css"; // Ajuste o caminho se necessário
import 'bootstrap/dist/css/bootstrap.min.css';
import 'bootstrap-icons/font/bootstrap-icons.css';

const HeaderUser = () => {
    const [activeSection, setActiveSection] = useState("pedidos");

    return (
        <div>
            {/* Cabeçalho Superior com Logo e Campo de Busca */}
            <div className="top-header">
                <div className="logo">
                    <img src="/organicflaivor.png" alt="Logo Organic Flavor" />
                </div>
                <div className="search-container">
                    <input
                        type="text"
                        placeholder="Buscar..."
                        className="header-input"
                    />
                    <i className="bi bi-search search-icon"></i> {/* Ícone de lupa */}
                </div>
            </div>

            <div className='flex'>
                <div className="sidebar">
                    {/* Ícones de seções */}
                    <div className="icon-menu">
                        <div
                            className={`icon-section ${activeSection === 'pedidos' ? 'active' : ''}`}
                            onClick={() => setActiveSection('pedidos')}
                        >
                            <i className="bi bi-house-door-fill"></i>
                            <span>Pedidos</span>
                        </div>
                        <div
                            className={`icon-section ${activeSection === 'entregas' ? 'active' : ''}`}
                            onClick={() => setActiveSection('entregas')}
                        >
                            <i className="bi bi-box"></i>
                            <span>Entregas</span>
                        </div>
                        <div
                            className={`icon-section ${activeSection === 'gerenciar' ? 'active' : ''}`}
                            onClick={() => setActiveSection('gerenciar')}
                        >
                            <i className="bi bi-person"></i>
                            <span>Gerenciar Usuários</span>
                        </div>
                        <div
                            className={`icon-section ${activeSection === 'faturamento' ? 'active' : ''}`}
                            onClick={() => setActiveSection('faturamento')}
                        >
                            <i className="bi bi-cash-stack"></i>
                            <span>Faturamento</span>
                        </div>
                        <div
                            className={`icon-section ${activeSection === 'manutencao' ? 'active' : ''}`}
                            onClick={() => setActiveSection('manutencao')}
                        >
                            <i className="bi bi-tools"></i>
                            <span>Manutenção</span>
                        </div>
                    </div>

                    {/* Ícones de notificações e usuário quase no fundo do header */}
                    <div className="notification-user">
                        <div className="notification-icon">
                            <i className="bi bi-bell-fill"></i>
                            <span className="notification-badge"></span> {/* Bolinha para notificação */}
                        </div>
                        <div className="user-icon">
                            <i className="bi bi-person-fill"></i>
                        </div>
                    </div>
                </div>

                {/* Área Central com o Card */}
                <div className="main-area">
                    <div className="card">
                        <h3>Título do Card</h3>
                        <p>Conteúdo do card vai aqui. Você pode adicionar mais informações ou outros componentes.</p>
                    </div>
                </div>
            </div>
        </div>
    );
};

export default HeaderUser;

CSS 


/* Sidebar (barra lateral) */
.sidebar {
    width: 170px;
    padding: 20px;
    background-color: #9983f0;
    display: flex;
    flex-direction: column;
    justify-content: flex-start; /* Alinha itens ao topo */
    height: 85vh;
}

.logo {
    display: flex;
    justify-content: center; /* Centraliza a imagem horizontalmente */
    margin: 20px 0; /* Adiciona espaço acima e abaixo da logo */
}

.logo img {
    max-width: 100%; /* Faz a imagem se ajustar à largura do contêiner */
    height: auto; /* Mantém a proporção da imagem */
}

/* Ícones à esquerda */
.icon-menu {
    display: flex;
    flex-direction: column;
    margin-bottom: 40px;
}

.icon-button {
    background-color: transparent;
    border: none;
    color: white;
    font-size: 24px;
    margin-bottom: 20px;
    cursor: pointer;
}

.icon-button.active {
    color: #ffcc66; /* Cor do ícone ativo */
}

.sidebar {
    position: relative; /* Para posicionar os ícones corretamente */
}

.icon-menu {
    display: flex; /* Para alinhamento horizontal dos ícones */
    flex-direction: column; /* Para manter ícones em coluna */
}

.notification-user {
    display: flex;
    align-items: center;
    position: absolute; /* Para posicionar quase no fundo do header */
    bottom: 20px; /* Distância do fundo do header */
    left: 20px; /* Distância da esquerda */
}

.notification-icon,
.user-icon {
    position: relative;
    margin-right: 15px; /* Espaçamento entre os ícones */
    font-size: 24px; /* Tamanho do ícone */
}

.notification-badge {
    position: absolute;
    top: -5px; /* Ajuste para centralizar verticalmente */
    right: -5px; /* Posição do badge ao lado do ícone */
    width: 8px; /* Largura da bolinha */
    height: 8px; /* Altura da bolinha */
    background-color: red; /* Cor da bolinha */
    border-radius: 50%; /* Formato circular */
}


/* Estilos para o cabeçalho superior */
.top-header {
    width: 100%; /* Aumenta a largura para 100% da tela */
    height: 90px; /* Altura do cabeçalho superior */
    background-color: #9983f0; /* Cor do fundo do cabeçalho superior */
    display: flex;
    align-items: center; /* Centraliza verticalmente o conteúdo */
    padding: 0 40px; /* Espaçamento interno */
    position: relative; /* Para o posicionamento correto com a barra lateral */
    z-index: 1; /* Coloca atrás da barra lateral */
}

/* Estilo da logo */
.logo {
    margin-right: 20px; /* Espaço entre a logo e o campo de busca */
}

.logo img {
    max-height: 70px; /* Ajuste a altura máxima da logo */
    height: auto; /* Mantém a proporção da imagem */
    margin-top: 10px; /* Adicione esse margin para descer a logo */
}


/* Estilos para o container de busca */
.search-container {
    position: relative; /* Para posicionar o ícone da lupa */
    margin-left: auto; /* Joga o container para a direita */
}

/* Estilos para o input do cabeçalho superior */
.header-input {
    width: 400px; /* Comprimento do input */
    padding: 10px 40px 10px 30px; /* Espaçamento interno do input, com espaço à esquerda para o ícone */
    border: none; /* Remove a borda padrão */
    border-radius: 15px; /* Borda arredondada */
    background-color: #b68cf8; /* Cor de fundo mais escura que a do header */
}

/* Remove o foco do input */
.header-input:focus {
    outline: none; /* Remove o contorno padrão ao focar no input */
}

/* Estilos para o ícone da lupa */
.search-icon {
    position: absolute; /* Para sobrepor ao input */
    left: 6px; /* Distância da borda esquerda */
    top: 50%; /* Centraliza verticalmente */
    transform: translateY(-50%); /* Ajusta para centralizar exatamente */
    color: white; /* Cor do ícone */
    font-size: 20px; /* Tamanho do ícone */
    cursor: pointer; /* Mão ao passar o mouse */
}

.flex {
    display: flex;
}

/* Estilo para a área central */
.main-area {
    flex: 1; /* Isso permite que a área principal ocupe o espaço restante */
    display: flex; /* Para usar flexbox */
    justify-content: flex-end; /* Alinha o conteúdo à direita */
    padding: 20px; /* Adiciona um pouco de espaçamento */
    background-color: #b68cf8; /* Cor do fundo mais escura que os headers */
}


/* Estilos para o card */
.card {
    background-color: white; /* Cor de fundo do card */
    border-radius: 10px; /* Borda arredondada */
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); /* Sombra sutil para o card */
    padding: 90px; /* Espaçamento interno do card */
    width: 300px; /* Largura do card */
    height: auto; /* Altura automática */
}

.icon-button {
    display: flex; /* Para alinhar ícone e texto */
    align-items: center; /* Centraliza verticalmente */
    background-color: transparent;
    border: none;
    color: white;
    font-size: 19px; /* Ajuste o tamanho da fonte */
    margin-bottom: 20px;
    cursor: pointer;
    position: relative;
    padding-left: -150px;
}

.icon-button span {
    margin-left: 10px; /* Espaçamento entre ícone e texto */
}

.icon-menu {
    display: flex;
    flex-direction: column;
    margin-bottom: 40px;
}

.icon-section {
    display: flex; /* Para alinhar ícone e texto */
    align-items: center; /* Centraliza verticalmente */
    color: white; /* Cor padrão do texto */
    font-size: 17px; /* Tamanho do texto */
    cursor: pointer; /* Mão ao passar o mouse */
    padding: 8px; /* Adiciona espaçamento interno */
    border-radius: 5px; /* Cantos arredondados */
    transition: background-color 0.3s; /* Transição suave */
}

.icon-section:hover {
    background-color: rgba(255, 204, 102, 0.2); /* Cor de fundo ao passar o mouse */
}

.icon-section.active {
    background-color: #ffcc66; /* Cor de fundo quando ativo */
    color: black; /* Muda a cor do texto quando ativo */
}
