<!--
// Copyright © 2020 Anticrm Platform Contributors.
// 
// Licensed under the Eclipse Public License, Version 2.0 (the "License");
// you may not use this file except in compliance with the License. You may
// obtain a copy of the License at https://www.eclipse.org/legal/epl-2.0
// 
// Unless required by applicable law or agreed to in writing, software
// distributed under the License is distributed on an "AS IS" BASIS,
// WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
// 
// See the License for the specific language governing permissions and
// limitations under the License.
-->
<script lang="ts">
  import Avatar from './Avatar.svelte'

  import { getName, Person } from '@hcengineering/contact'
  import { Asset } from '@hcengineering/platform'
  import { AnySvelteComponent, IconSize } from '@hcengineering/ui'

  export let value: Person
  export let subtitle: string | undefined = undefined
  export let size: IconSize
  export let icon: Asset | AnySvelteComponent | undefined = undefined
</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<div class="flex-row-center" on:click>
  <Avatar avatar={value.avatar} {size} {icon} />
  <div class="flex-col min-w-0 {size === 'tiny' || size === 'inline' ? 'ml-1' : 'ml-2'}">
    {#if subtitle}<div class="content-dark-color text-sm">{subtitle}</div>{/if}
    <div class="content-accent-color overflow-label text-left">{getName(value)}</div>
  </div>
</div>