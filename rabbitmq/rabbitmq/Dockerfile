FROM rabbitmq:3.11-management

RUN apt-get update && apt-get install -y curl --no-install-recommends && rm -rf /var/lib/apt/lists/*


ENV RABBITMQ_DELAYED_PLUGIN_VERSION=3.11.1
RUN curl -L https://github.com/rabbitmq/rabbitmq-delayed-message-exchange/releases/download/${RABBITMQ_DELAYED_PLUGIN_VERSION}/rabbitmq_delayed_message_exchange-${RABBITMQ_DELAYED_PLUGIN_VERSION}.ez > /opt/rabbitmq/plugins/rabbitmq_delayed_message_exchange.ez

COPY enabled_plugins /etc/rabbitmq/

RUN chown -R rabbitmq:rabbitmq /etc/rabbitmq/enabled_plugins /opt/rabbitmq/plugins/rabbitmq_delayed_message_exchange.ez
