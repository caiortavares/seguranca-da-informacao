Source Address: 10.1.3.252

Source OSPF Router: 1.1.1.1

Network Mask: 255.255.255.0



Source Address: 10.1.3.251

Source OSPF Router: 2.2.2.2

Network Mask: 255.255.255.192



Ao coletar as informações acima por meio do Wireshark, pode-se concluir

que o problema na rede se dá por conta de divergência na máscara de sub-rede.



O roteador 1 tem a máscada pré-definida como 255.255.255.0 (/24), 

enquanto o roteador 2 está com a máscara configurada como 255.255.255.192 (/26). 



Embora os endereços IP (10.1.3.252 e 10.1.3.251) estejam dentro do intervalo de ambas as sub-redes, o OSPF exige que a máscara de rede seja idêntica nos dois dispositivos para que a adjacência seja formada. A diferença nas máscaras (/24 vs. /26) faz com que os roteadores considerem que estão em sub-redes diferentes, impedindo a formação da adjacência OSPF e, consequentemente, a conectividade.





