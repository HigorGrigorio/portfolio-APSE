# [<- Voltar]($root$/../../../Projeto%20de%20software/main.md)

> # Esquema textual

    Medicao (id_sensor, valor, fk_Sensor_id_sensor)
        fk_Sensor_id_sensor references Sersor(id_sensor)

    Sensor (id_sensor, fk_TipoSensor_tipo)
        fk_TipoSensor_tipo references TipoSensor(tipo)

    TipoSensor (tipo)

    Kit (fk_Cliente_id_cliente, fk_Carrinho_id_carrinho)
        fk_Cliente_id_cliente references Cliente(id_cliente)
        fk_Carrinho_id_carrinho references Carrinho(id_carrinho)

    Carrinho(id_carrinho, data_criacao, quantidade, fk_Cliente_id_cliente)
        fk_Cliente_id_cliente references Cliente(id_cliente)

    Cliente(ir_cliente, nome, email, senha, cpf, data_nascimento, email_secundario, fk_Endereco_cep)
        fk_Endereco_cep references Endereco(cep)

    Endereco (cep, numero, fk_Cidade_nome, fk_Bairro_nome, fk_Logradouro_nome)
        fk_Cidade_nome references Cidade(nome)
        fk_Bairro_nome references Bairro(nome)
        fk_Logradouro_nome references Logradouro(nome)

    Bairro(nome, fk_Cidade_nome)
        fk_Cidade_nome references Cidade(nome)

    Cidade(nome, fk_Estado_nome)
        fk_Estado_nome references Estado(nome)

    Estado(nome, fk_Estado_nome)
        fk_Estado_nome references Estado(nome)

    Bairro(nome, fk_TipoLogradouro_tipo)
        fk_TipoLogradouro_tipo references TipoLogradouro(tipo)

    TipoLogradouro(tipo)

    Compra (id_compra, data, valor, fk_Cartao_numero, fk_Carrinho_id_carrinho, fk_Cliente_id_cliente)
        fk_Cliente_id_cliente references Cliente(id_cliente)
        fk_Carrinho_id_carrinho references Carrinho(id_carrinho)
        fk_Cartao_numero references Cartao(numero)

    Cartao(tipo, numero, agencia, fk_Cliente_id_cliente)
        fk_Cliente_id_cliente references Cliente(id_cliente)

    Reclamacao (id_reclamacao, descricao, data, hora, fk_Cliente_id_cliente, fk_Compra_id_compra)
        fk_Cliente_id_cliente references Cliente(id_cliente)
        fk_Compra_id_compra references Compra(id_compra)

    Troca (id_troca, descricao, data, hora, tipo, fk_Cliente_id_cliente)
        fk_Cliente_id_cliente references Cliente(id_cliente)

    CompraTroca (fk_Compra_id_compra, fk_Troca_id_troca)
        fk_Compra_id_compra references Compra(id_compra)
        fk_Troca_id_troca references Troca(id_troca)