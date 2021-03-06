---
id: permissions
title: Understanding Rythm's Permissions
---

## What users can use what command?

Rythm's built-in permission system can be divided into the following groups:

### Normal user without any special roles
 - Is able to add songs to the queue but can't remove other users' songs (can remove their own)
 - Is able to use commands that don't interfere with other people's music.
   - `lyrics`, `np`, `queue`, etc.
 - Can't skip a song without voting.
 - Doesn't have access to control the music in any way.

### User alone with Rythm/User with a `DJ` role or the `Manage Channels` permission
:::info note
This includes all other users in the voice chat being deafened.
:::
 - Has full access to all music commands.
 - Can't change Rythm's settings.

**Note**: If there isn't a role named `DJ` in your server, one can be created with no special permissions assigned and they will still be able to access these features.

### User with `Manage Server` permission
 - Is able to change Rythm's settings.
 - Is limited to normal user's music commands, unless they have `Manage Channels` permission or `DJ` role.

### User with `Administrator` permission
 - Is able to change Rythm's settings.
 - Has full access to all music commands.

## How can I block music commands in a specific text channel?
You can use `!settings blacklist #channels` to blacklist specific text channels.

**Example**: `!settings blacklist #chat #gaming #international...`

![Blacklist example](/img/docs/settings/blacklist-text-channel-example.png)

<details>
<summary>Alternatively, you can use Discord's permission system if you don't want any blacklisted channel messages.</summary>
<img src="/img/docs/perms/deny-rythm.png" alt="deny rythm"/>
</details><br/>

## How can I make Rythm only respond to Admins/specific roles?
In order to make Rythm commands just available to specific roles, you can do the following:

### DJ Only Mode
:::info note
If someone is alone with Rythm, they are able to use Rythm regardless of having a `DJ` role/`Manage Channel` permission.
:::

 1. Give those you want to have access a role named `DJ`
 2. Run `!settings djonly on`

### Blacklisting Channels
 1. Make a channel that can only be seen by users with the specific role.
    <details>
        <summary>Click here for how.</summary>
        <ol>
            <li><img src="/img/docs/perms/role-1.png" alt="role 1"/></li>
            <li><img src="/img/docs/perms/role-2.png" alt="role 2"/></li>
        </ol>
        <ul>
            <li>More information on how to do this can be found at <a href="https://support.discord.com/hc/en-us/articles/206029707">Discord's support page.</a></li>
        </ul>
    </details>
 2. Blacklist all other text channels with Rythm's blacklist function. To blacklist channels, use the following command: `!settings blacklist #channel #channel2...`
 
    **Example**: `!settings blacklist #chat #gaming #international...`<br/>

    ![blacklist example](/img/docs/settings/blacklist-text-channel-example.png)

    <details>
    <summary>Alternatively, you can use Discord's permission system if you don't want any blacklisted channel messages.</summary>
    <img src="/img/docs/perms/deny-rythm.png" alt="deny rythm"/>
    </details>



## How can I give all users access to all music commands?
There is currently no setting that will apply DJ to all users. You will have to either give them the `Manage Channels` permission or the DJ role manually.

If every member in your server has a common role, you can use the following settings command to set that role to be DJ Role: `!settings djrole <Role name> / <@Role>`. To learn more, head to the [DJ role setting section](/settings/#dj-role).
:::info note
Users alone in a voice channel with Rythm will be treated as though they have the DJ role until another user joins the voice channel with them even if they have no roles. Members with the `DJ` role will not be able to change any of Rythm's settings.
:::

## How do I restrict Rythm from joining a voice channel?
To disallow Rythm from being used within certain voice channels, you must use the Discord permission system.

1. Go to your server's settings and select `Roles`.
2. Find Rythm, revoke its `Administrator` permission and grant the `Read Text Channels & See Voice Channels`, `Send Messages`, `Manage Messages`, `Embed Links`, `Add Reactions`, `Connect` and `Speak` permissions.
   - If you have any other roles Rythm is assigned to, repeat this step for each role.
3. Save and close out of server settings.
4. Go to each voice channel you want to restrict Rythm from connecting to.
5. Click `Edit Channel` ➠ `Permissions` ➠ `Add` ➠ `Rythm`
6. Deny the `Connect` permission on the Rythm override.
7. Save and close out of channel settings.
