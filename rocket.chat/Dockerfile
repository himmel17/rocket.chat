FROM rocket.chat:0.68.4
LABEL maintainer="himmel17"
LABEL title="rocket.chat for custom user"
LABEL version="0.1"
LABEL description="rocket.chat for custom user"

ARG user_name="0000133057"
ARG user_id=1001
ARG group_name="rsd"
ARG group_id=1001

# ユーザ設定
# ユーザID,グループIDをパラメータにすることでホストボリュームに対する操作を
# ユーザ権限で実行できるようにしている．
USER root
RUN groupadd -g ${group_id} ${group_name} && \
	useradd --create-home --shell /bin/bash \
	--uid ${user_id} --gid ${group_id} --home-dir /home/${user_name} \
	${user_name}

USER ${user_name}
# WORKDIR /home/${user_name}
# ENV HOME /home/${user_name}

CMD ["node", "main.js"]
