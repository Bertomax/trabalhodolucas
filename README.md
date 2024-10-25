
// Classe Fachada
public class PedidoFachada {
    private EstoqueService estoqueServico;
    private PagamentoServico pagamentoServico;
    private FaturaService faturaServico;
    private EnvioServico entregaServico;

    public PedidoFachada() {
        this.estoqueServico = new EstoqueServico();
        this.pagamentoServico = new PagamentoServico();
        this.faturaServico = new FaturaServico();
        this.entregaServico = new EntregaServico();
    }

    public void fazerPedido(Pedido pedido) {
        if(estoqueServico.checkEstoque(pedido)) {
            pagamentoServico.processarPagamento(pedido);
            envioServico.calcularEnvio(pedido);
            faturaServico.gerarFatura(pedido);
        } else {
            System.out.println("Item out of stock");
        }
    }
}

// Subsistema de Serviço de Estoque
public class EstoqueServico {
    public boolean checarEstoque(Pedido pedido) {
        // Lógica para verificar estoque
        return true;
    }
}

// Subsistema de Serviço de Pagamento
public class PagamentoServico {
    public void processarPagamento(Pedido pedido) {
        // Lógica para processar pagamento
    }
}

// Subsistema de Serviço de Fatura
public class FaturaServico {
    public void gerarFatura(Order order) {
        // Lógica para gerar fatura
    }
}

// Subsistema de Serviço de Envio
public class EnvioServico {
    public void calcularEnvio(Pedido pedido) {
        // Lógica para calcular envio
    }
}
// Classe de Pedido
public class Pedido {
    // Detalhes do pedido
}
