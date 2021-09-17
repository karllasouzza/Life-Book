<template>
  <section>
    <Logo />
    <main>
      <header>
        <Labels :text="login" />
        <Labels :text="account" />
      </header>
      <form>
        <div>
          <h1>{{ msg }}</h1>
          <LabelsInfo target="" :text="info" />
        </div>
        <div>
          <LabelsInfo target="name" :text="info_name" />
          <Inputs id="name" ref="ref_name" v-model="name" type="text" />
        </div>
        <div>
          <LabelsInfo target="password" :text="info_passWord" />
          <Inputs
            id="password"
            ref="ref_passWord"
            v-model="password"
            hiden="true"
            :type="type_password"
          />
        </div>
        <ButtonPrimary :text="text_button" />
        <p>
          <span>{{ reset_password }}</span
          ><labels :text="reset_password_target" />
        </p>
      </form>
    </main>
  </section>
</template>

<script>
import Logo from '~/components/Icons/Logo.vue'
import Inputs from '~/components/Inputs.vue'

export default {
  data() {
    return {
      // Header
      login: 'Entrar',
      account: 'Criar Conta',

      // Form
      msg: 'Bem vindo de volta',
      info: 'Entre com sua conta',
      info_name: 'Nome de usuário',
      info_passWord: 'Senha',
      type_password: 'password',
      text_button: 'Entrar',
      reset_password: 'Esqueceu a senha?',
      reset_password_target: 'Resete aqui',

      // V-modal
      password: '',
      name: '',
    }
  },
  components: {
    Logo,
    Inputs,
  },
}
</script>

<style scoped>
section {
  width: 100%;
  height: 100%;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;

  background: var(--primary) url(~/assets/img/DECORATION.png);
  background-position: center;
  background-size: cover;
}

section > svg {
  height: 70px;
  margin: auto 0;
}

section > main {
  width: 100%;
  height: 77%;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  justify-self: flex-end;

  border-radius: 25px 25px 0 0;
  background: var(--second);
}

section > main > header {
  width: 100%;
  height: 55px;

  display: flex;
  align-items: center;
  justify-content: space-around;

  border-radius: 20px 20px 0 0;
}

section > main > form {
  width: 100%;
  height: 100%;

  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;

  background: var(--primary);

  border-radius: 25px 25px 0 0;
}

main > form > div {
  width: 80%;
  height: 45px;

  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: space-between;
}

form > div > h1 {
  margin-bottom: 8px;
}

form > p {
  width: 80%;

  display: flex;
  justify-content: space-around;
}

form > p > button {
  color: var(--second);
}
</style>
