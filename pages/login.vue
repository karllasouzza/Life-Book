<template>
  <section>
    <Logo :class="!chang ? 'logo_account' : ''"  />
    <main :class="!chang ? 'form_account' : ''">
      <header>
        <Labels :text="login" :style="{color: chang ? '#fff' : 'rgba(255, 255, 255, 0.25)'}" @click.native="chang = true" />
        <Labels :text="account" :style="{color: !chang ? '#fff' : 'rgba(255, 255, 255, 0.25)'}" @click.native="chang = false" />
      </header>
      <!-- Login -->
      <form v-if="chang === true" >
        <div>
          <h1>{{ msg }}</h1>
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
            type="password"
          />
        </div>
        <ButtonPrimary :text="text_button" />
        <p>
          <span>{{ reset_password }}</span
          ><labels :text="reset_password_target" />
        </p>
      </form>
      <!-- Create account -->
      <form v-else>
        <div>
          <h1>{{ msg_account }}</h1>
        </div>
        <!-- Email  -->
        <div>
          <LabelsInfo target="email" :text="info_email" />
          <Inputs id="email" ref="ref_email" v-model="email" type="email" />
        </div>
        <!-- Name  -->
        <div> 
          <LabelsInfo target="name" :text="info_name" />
          <Inputs id="name" ref="ref_name" v-model="name" type="text" />
        </div>
        <!-- PassWord  -->
        <div>
          <LabelsInfo target="password" :text="info_passWord" />
          <Inputs
            id="password"
            ref="ref_passWord"
            v-model="password"
            hiden="true"
            type="password"
          />
        </div>
        <!-- Confirm to PassWord  -->
        <div>
          <LabelsInfo target="password_confirm" :text="info_passWord_confirm" />
          <Inputs
            id="password_confirm"
            ref="ref_passWord_confirm"
            v-model="password_confirm"
            hiden="true"
            type="password"
          />
        </div>
        <ButtonPrimary :text="text_button" />
      </form>
    </main>
  </section>
</template>

<script>
import Logo from '~/components/Icons/Logo.vue'
import Inputs from '~/components/Inputs.vue'

export default {
  components: {
    Logo,
    Inputs,
  },
  data() {
    return {
      // Header
      login: 'Entrar',
      account: 'Criar Conta',
      chang: true,

      // Form
      msg: 'Bem vindo de volta',
      msg_account: 'Seja Bem Vindo',
      info_email: 'Email',
      info_name: 'Nome de usuário',
      info_passWord: 'Senha',
      info_passWord_confirm: 'Confirmar Senha',

      text_button: 'Entrar',
      reset_password: 'Esqueceu a senha?',
      reset_password_target: 'Resete aqui',

      // V-modal
      email: '',
      name: '',
      password: '',
      password_confirm: ''
    }
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

.logo_account{
  height: 65px;
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

.form_account{
  height: 84%;  
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
