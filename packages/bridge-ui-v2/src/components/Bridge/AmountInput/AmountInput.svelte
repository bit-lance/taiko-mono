<script lang="ts">
  import { t } from 'svelte-i18n';

  import { InputBox } from '$components/InputBox';
  import { uid } from '$libs/util/uid';

  import Balance from './Balance.svelte';

  let inputId = `input-${uid()}`;
</script>

<div class="AmountInput f-col space-y-2">
  <div class="f-between-center text-secondary-content">
    <label class="body-regular" for={inputId}>{$t('amount_input.label')}</label>
    <Balance />
  </div>
  <div class="relative f-items-center">
    <InputBox
      id={inputId}
      type="number"
      placeholder="0.01"
      min="0"
      class="w-full input-box outline-none py-6 pr-16 px-[26px] title-subsection-bold placeholder:text-tertiary-content" />
    <button class="absolute right-6 uppercase">{$t('amount_input.button.max')}</button>
  </div>
</div>