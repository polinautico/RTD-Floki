.. _Painel Solar e Baterias:

Módulo Solar e Baterias
====

Resumo do sistema
----
Para um barco solar é essencial o sistema de recarregamento das baterias através dos painéis solares. O regarregamento das baterias é feita por intermédio do controlador de carga, conforme veremos a seguir.

.. figure:: https://raw.githubusercontent.com/polinautico/RTD-Floki/main/docs/source/diagramas/esquematico_painel_solar.drawio.png
   :align: center

   Resumo do circuito

Painéis Solares
----

Os módulos fotovoltáicos do Floki são os `ZNSHINE ZXP6-LD72-330/P <https://github.com/polinautico/RTD-Floki/blob/main/docs/source/datasheets/Datasheet-ZN-325-350-poly.pdf>`_.
- Cada painél tem uma área útil de 1,96m² e conta com 16,82% de eficiência.

Os painéis foram arranjados em série para evitar perdas na linha, bem como usar fios de menor diâmetro.

.. figure:: https://raw.githubusercontent.com/polinautico/RTD-Floki/main/docs/source/imagens/painel_solar_config.png
   :align: center

   Arranjo dos módulos solares

Banco de Baterias
----

Pelo `edital do DSB <https://desafiosolar.com.br/regras/>`_ temos a seguinte condição:

``"5.2.2.As embarcações devem estar equipadas com um banco de baterias de capacidade nominal máxima permitida de 2075 Wh. Todas as seguintes referências à “bateria” dizem respeito ao banco de bateria. A capacidade nominal é baseada num tempo de descarga de 01 (uma) hora e será verificada inicialmente pela folha de dados do fabricante, que deve ser enviada com antecedência por e-mail para a Comissão Técnica do DSB.""``

O Banco de Baterias do Floki é composto por 4 GP12-65. Ou seja, o barco conta com 4 baterias de 12V formando um banco de 48V, com capacidade limitada pelo edital do :ref:`DSB`

.. figure:: https://raw.githubusercontent.com/polinautico/RTD-Floki/main/docs/source/diagramas/Banco_de_Baterias.png
   :align: center

   Banco de Baterias



Controlador de Carga
----

Para permitir a máxima eficiência dos painés, regular o carregamento das baterias e realizar diversas medições, a embarcação conta com o Controlador de Carga `Epever Tracer 5415AN <https://github.com/polinautico/RTD-Floki/raw/main/docs/source/datasheets/Tracer-AN50-100A-Manual-EN-V3.1.pdf>`_

O controlador de carga tem uma interface de dados RS-485 que permite a telemetria de todos os seus dados. Essa parte é documentada na seção de :ref:`Sensores e Telemetria`

.. figure:: https://raw.githubusercontent.com/polinautico/RTD-Floki/main/docs/source/imagens/circuito/EpeverTracer5415AN.png
   :align: center

   Epever Tracer 5415AN


Circuito Painel-MPPT-Bateria
----

* Para associar os painés em série é necessário conectar o polo positivo de um painél no polo negativo do outro. Os dois pólos resultantes devem ser conectados no Controlador de Carga nos bornes específicos para o painél solar.
* Para associar as baterias em série é necessário conectar o polo positivo de uma bateria no polo negativo da outra. Os dois pólos resultantes devem ser conectados no Controlador de Carga nos bornes específicos para a bateria.

.. figure:: https://raw.githubusercontent.com/polinautico/RTD-Floki/main/docs/source/diagramas/painel_solar_mppt_bateria.png
   :align: center

   Esquemático para o circuito "Painel-MPPT-Bateria"