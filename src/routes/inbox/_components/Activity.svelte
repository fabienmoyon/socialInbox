<script>
export let item;
export let email;

import WorkSpaceActivityEmailShared from './Activity/EmailShared.svelte';
import WorkSpaceActivityChatStarted from './Activity/ChatStarted.svelte';
import WorkSpaceActivityEmailLabelAdded from './Activity/EmailLabelAdded.svelte';
import WorkSpaceActivityEmailLabelRemoved from './Activity/EmailLabelRemoved.svelte';
import WorkSpaceActivityEmailTaskCreated from './Activity/EmailTaskCreated.svelte';
import EmailTaskDoneStatusUpdated from './Activity/EmailTaskDoneStatusUpdated.svelte';

const compMap = {
  'email:share': WorkSpaceActivityEmailShared,
  'chat:started': WorkSpaceActivityChatStarted,
  'email:label:added': WorkSpaceActivityEmailLabelAdded,
  'email:label:removed': WorkSpaceActivityEmailLabelRemoved,
  'email:task:created': WorkSpaceActivityEmailTaskCreated,
  'email:task:done-status:updated': EmailTaskDoneStatusUpdated,
};

</script>

<svelte:component this="{compMap[item.name]}" {email} activity="{item}" />
