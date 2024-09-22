<template>
    <div class="text-box">
        <h1><i>Desenvolvemos sites funcionais e otimizados para transformar sua presença digital em resultados reais.</i></h1>
        <p>A OminiString é uma startup criada na Unimar, <b>dedicada ao desenvolvimento de sites eficientes e seguros.</b> Unimos inovação e conhecimento técnico para transformar <b>negócios</b> no ambiente digital.</p>
        <a href="" class="btn">Ver planos</a>
        <div class="parceiros">
            <div class="shadow1"></div>
            <div class="shadow2"></div>
            <div class="parceiros-container">
                <img src="https://i.imgur.com/K3NV7Q6.png" alt="Parceiro 1" />
                <img src="https://i.imgur.com/Y3hsgqk.png" alt="Parceiro 2" />
                <img src="https://i.imgur.com/F1olfmY.png" alt="Parceiro 3" />
                <img src="https://i.imgur.com/K3NV7Q6.png" alt="Parceiro 1" />
                <img src="https://i.imgur.com/Y3hsgqk.png" alt="Parceiro 2" />
                <img src="https://i.imgur.com/F1olfmY.png" alt="Parceiro 3" />
                <img src="https://i.imgur.com/K3NV7Q6.png" alt="Parceiro 1" />
                <img src="https://i.imgur.com/Y3hsgqk.png" alt="Parceiro 2" />
                <img src="https://i.imgur.com/F1olfmY.png" alt="Parceiro 3" />
                <img src="https://i.imgur.com/K3NV7Q6.png" alt="Parceiro 1" />
                <img src="https://i.imgur.com/Y3hsgqk.png" alt="Parceiro 2" />
                <img src="https://i.imgur.com/F1olfmY.png" alt="Parceiro 3" />
                <img src="https://i.imgur.com/K3NV7Q6.png" alt="Parceiro 1" />
                <img src="https://i.imgur.com/Y3hsgqk.png" alt="Parceiro 2" />
                <img src="https://i.imgur.com/F1olfmY.png" alt="Parceiro 3" />
                <img src="https://i.imgur.com/K3NV7Q6.png" alt="Parceiro 1" />
                <img src="https://i.imgur.com/Y3hsgqk.png" alt="Parceiro 2" />
                <img src="https://i.imgur.com/F1olfmY.png" alt="Parceiro 3" />
                <img src="https://i.imgur.com/K3NV7Q6.png" alt="Parceiro 1" />
                <img src="https://i.imgur.com/Y3hsgqk.png" alt="Parceiro 2" />
                <img src="https://i.imgur.com/F1olfmY.png" alt="Parceiro 3" />
                <img src="https://i.imgur.com/K3NV7Q6.png" alt="Parceiro 1" />
                <img src="https://i.imgur.com/Y3hsgqk.png" alt="Parceiro 2" />
                <img src="https://i.imgur.com/F1olfmY.png" alt="Parceiro 3" />
                
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'AppHero',
    props: {
        msg: String
    }
}
</script>

<style scoped>
.text-box {
    max-width: 42rem;
    display: flex;
    flex-direction: column;
    gap: 40px;

    & h1 {
        font-size: 2.5rem;
        line-height: 1.2;
    }

    & p {
        max-width: 35rem;
    }

    & b {
        color: #6A0DAD;
    }
}

.parceiros {
    position: relative;
    position: relative;
    overflow: hidden;
    background-color: #F5F5F5;
    white-space: nowrap; 
}

.parceiros-container {
    display: inline-flex;
    gap: 20px;
    animation: move 100s linear infinite; /* Animação contínua de 10 minutos */
}
.parceiros-container img {
    height: 40px;
    filter: brightness(0);
}

@keyframes move {
    0% {
        transform: translateX(0);
    }
    100% {
        transform: translateX(-50%); /* Move todas as logos para a esquerda */
    }
}

.shadow1 {
    left: 0;
    position: absolute;
    width: 15%;
    height: 100%;
    background-image: linear-gradient(to right, #f5f5f5, #f5f5f500);
    z-index: 100;
}

.shadow2{
    right: 0;
    position: absolute;
    width: 15%;
    height: 100%;
    background-image: linear-gradient(to left, #f5f5f5, #f5f5f500);
    z-index: 100;
}

@media (max-width: 750px) { 
    .text-box {
    width: 20rem; 
    margin: auto;
    padding: 15px; 
    display: flex;
    flex-direction: column; 
    gap: 40px; 
}

h1 {
    margin-top: 20px;
    font-size: 2rem !important; 
    line-height: 1.2;
}

p {
    font-size: 14px;
    width: 15rem; 
}

b {
    color: #6A0DAD;
}

.parceiros {
    position: relative;
    overflow: hidden;
    background-color: #F5F5F5;
    white-space: nowrap; 
}

.parceiros-container {
    display: inline-flex;
    gap: 15px; 
    animation: move 100s linear infinite;
}

.parceiros-container img {
    height: 30px; 
    filter: brightness(0);
}

@keyframes move {
    0% {
        transform: translateX(0);
    }
    100% {
        transform: translateX(-50%); 
    }
}

.shadow1 {
    left: 0;
    position: absolute;
    width: 15%;
    height: 100%;
    background-image: linear-gradient(to right, #f5f5f5, #f5f5f500);
    z-index: 100;
}

.shadow2 {
    right: 0;
    position: absolute;
    width: 15%;
    height: 100%;
    background-image: linear-gradient(to left, #f5f5f5, #f5f5f500);
    z-index: 100;
}
}
</style>
