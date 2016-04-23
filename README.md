# vetor-
Esses pontos são:

a) No lado esquerdo da tela, quando x <= 0;
b) No lado direito da tela, quando x, somado ao largura da bola, for maior que a largura da tela;
c) No topo da tela, quando y <= 0;
d) Na base da tela, quando y, somado a altura da bola, for maior que a altura da tela.

Quando essa colisão ocorrer, devemos reposicionar a bola no interior da tela, e então inverter a velocidade em x ou y, de acordo com o local onde a bola colidiu. Em código, temos o seguinte:
?
private void checkCollision()
{
    //Testamos se a bola saiu da tela
    //Se sair, recolocamos na tela e invertemos a velocidade do eixo
    //Isso fará a bola "quicar".        
    if (x < 0) { //Lateral esquerda
        vx = -vx;
        x = 0;
    } else if ((x+SIZE) > screenWidth) { //Lateral direita
        vx = -vx;
        x = screenWidth - SIZE;
    }
     
    if (y < 0) { //topo
        vy = -vy;
        y = 0;
    } else if (((y+SIZE) > screenHeight)) { //baixo
        vy = -vy;
        y = screenHeight - SIZE;
    }
}

E esta é a fase de atualização da bola. 



&lt;?hh
