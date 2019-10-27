<script>
  import Poll from "../../common/Poll.svelte";
  import Button, { Label } from "@smui/button";
  import { Link } from "svelte-routing";

  let valueOutlinedEnhanced;
  let result = Math.floor(Math.random() * 3);
  while (document.res === result) {
    result = Math.floor(Math.random() * 3);
  }
  document.res = result;
</script>

<style>
  .done-icon {
    background-size: auto;
    width: 290px;
    height: 290px;
    margin: auto;
    border-radius: 100%;
    border: 12px #54b4ee solid;
    box-sizing: border-box;
  }
  .done-icon0 {
    background: url(/assets/icons/0.svg) no-repeat 50% 50%;
  }
  .done-icon1 {
    background: url(/assets/icons/1.svg) no-repeat 50% 50%;
  }
  .done-icon2 {
    background: url(/assets/icons/2.svg) no-repeat 50% 50%;
  }
  .done-title {
    font-size: 24px;
  }
  .done {
    text-align: center;
  }
  .info {
    font-size: 14px;
    color: #8b8b8b;
    margin-bottom: 20px;
  }
  .social {
    width: 100px;
    display: flex;
    margin: 8px auto;
    justify-content: space-between;
  }
  .vk {
    background: url(/assets/icons/vk.svg) no-repeat 50% 50%;
    width: 28px;
    height: 28px;
  }
  .twitter {
    background: url(/assets/icons/twitter.svg) no-repeat 50% 50%;
    width: 28px;
    height: 28px;
  }
  .inst {
    background: url(/assets/icons/insta.svg) no-repeat 50% 50%;
    width: 28px;
    height: 28px;
  }
  .share {
    font-size: 12px;
    color: #8b8b8b;
  }
  .controls {
    display: grid;
    grid-gap: 4px;
  }
</style>

<div class="done">
  {#if result === 0}
    <div class="done-icon done-icon0" />
    <h1 class="done-title">
      Больше всего ты похож<br />
      на Лаврова!
    </h1>
    <div class="info">
      Это Министр иностранных дел,<br>
      если ты вдруг не знал! Будь как он, <br>
      поднимай экономику России!<br>
      <br>
      Нажимая на кнопку ниже, у тебя есть возможность<br>
      узнать больше о Лаврове и о других,<br>
      интересующих тебя чиновниках
    </div>
  {:else if result === 1}
    <div class="done-icon done-icon1" />
    <h1 class="done-title">
      Твой чиновник -<br>
      Эльвира Набиуллина
    </h1>
    <div class="info">
      Она Председатель ЦБ РФ.<br>
      Держу в курсе! Это уникальная личность!<br>
      И ты можешь такой стать!<br>
      <br>
      Нажимая на кнопку ниже, у тебя есть возможность<br>
      узнать больше о Набиуллиной и о других,<br>
      интересующих тебя чиновниках
    </div>
  {:else if result === 2}
    <div class="done-icon done-icon2" />
    <h1 class="done-title">
      Ты - Шойгу!<br>
      Шучу, просто уровень<br>
      жизни совпадает!
    </h1>
    <div class="info">
      Это Министр обороны РФ!<br>
      Держу в курсе!<br>
      <br>
      Нажимая на кнопку ниже, у тебя есть возможность<br>
      узнать больше о Шойгу и о других,<br>
      интересующих тебя чиновниках
    </div>
  {/if}
  <div class="controls">
    <a href="http://declarator.web.app">
      <Button variant="raised">
        <Label>Больше информации</Label>
      </Button>
    </a>

    <Link to="/incom">
      <Button variant="raised">
        <Label>Пройти тест “Угадай доход”</Label>
      </Button>
    </Link>
  </div>
  <div class="social">
    <div class="vk" />
    <div class="twitter" />
    <div class="inst" />
  </div>
  <div class="share">Расскажи друзьям!</div>
</div>
