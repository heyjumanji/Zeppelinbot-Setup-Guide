![Banner](Assets/Zeppelin.png)
# Introduction
This guide is made by keeping in mind to help all the new user who want to setup the bot and facing some problem with setup their config commands and files. Well no worries this will help you out everything, as im making this guide because one day im facing alot of problems and it took me alot of time to understand and set-up the bot. This guide is only for beginners who have never setup this bot before and not used the bot as i said i have got alot of problems to setup the bot and also somehow the community of the bot is rude to me and quite not kind to me to help and dont gives answer to my questions of my problems which im facing with the bot to setup, so here we comes just read and follow the guide you will understand everything:3

---

# What is Zeppelinbot ?
> Zeppelin is a private moderation bot for Discord, designed with large servers and reliability in mind. This bot as said it is a private bot so it can be only invite by request.

## Resources:
• [offical website](https://zeppelin.gg/)

• [Official Documentation](https://zeppelin.gg/doc)

[![Join our Discord server!](https://invidget.switchblade.xyz/9bCGvGw5rT)](http://discord.gg/9bCGvGw5rT)

# How to setup ?
Well no worries just copy and paste this config code below to start with the bot. Just you need to replace the mod, admin and other logs channels id and your good to goo! Just once check the confirmation and you will see where you need to be replaced theod, admin and channel ids.
```
prefix: '!' 

levels:
  "Admin role id": 100 #admin role
  "Mod role id": 50  #Mod role

plugins:

  #Phisherman
  phisherman:
    config:
      api_key: "your key"

  #Reminders
  reminders:
    replaceDefaultOverrides: true
    overrides:
      - level: '>=50'
        config:
          can_use: true

  #Mod Actions
  mod_actions:
    config:
      dm_on_kick: true
      dm_on_ban: true
      dm_on_warn: true
      message_on_warn: true
      message_on_kick: true
      message_on_ban: true
      message_channel: null
      warn_message: '**You have been warned in {guildName} for:** {reason}!!'
      kick_message: '**You have been kicked from {guildName}.** **Reason given:** {reason}'
      ban_message: '**You have been banned from {guildName}.** **Reason given:** {reason}'
      tempban_message: >-
        **You have been banned from {guildName} for {banTime}.** **Reason
        given:** {reason}
      alert_on_rejoin: false
      alert_channel: null
      warn_notify_enabled: false
      warn_notify_threshold: 5
      warn_notify_message: |-
        The user already has **{priorWarnings}** warnings!
        Please check their prior cases and assess whether or not to warn anyways.
        Proceed with the warning?
      ban_delete_message_days: 1
      can_note: false
      can_warn: false
      can_mute: false
      can_kick: false
      can_ban: false
      can_unban: false
      can_view: false
      can_addcase: false
      can_massunban: false
      can_massban: false
      can_massmute: false
      can_hidecase: false
      can_deletecase: false
      can_act_as_other: false
      create_cases_for_manual_actions: true
    overrides:
      - level: '>=50'
        config:
           can_deletecase: true
           can_note: true
           can_warn: true
           can_mute: true
           can_kick: true
           can_ban: true
           can_unban: true
           can_view: true
           can_addcase: true
      - level: '>=100'
        config:
          can_massunban: true
          can_massban: true
          can_massmute: true
          can_hidecase: true
          can_act_as_other: true

  #Slowmode
  slowmode:
    config:
      use_native_slowmode: true
      can_manage: false
      is_affected: true
    overrides:
    - level: '>=50'
      config:
        can_manage: true
        is_affected: false

  #Utility
  utility:
    config:
      can_roles: false
      can_level: false
      can_search: false
      can_clean: false
      can_info: false
      can_server: false
      can_inviteinfo: false
      can_channelinfo: false
      can_messageinfo: false
      can_userinfo: true
      can_roleinfo: false
      can_emojiinfo: false
      can_snowflake: false
      can_reload_guild: false
      can_nickname: false
      can_ping: false
      can_source: false
      can_vcmove: false
      can_vckick: false
      can_help: false
      can_about: false
      can_context: false
      can_jumbo: false
      jumbo_size: 128
      can_avatar: false
      info_on_single_result: true
      autojoin_threads: true
    overrides:
      - level: '>=50'
        config:
          can_roles: true
          can_level: true
          can_search: true
          can_clean: true
          can_info: true
          can_server: true
          can_inviteinfo: true
          can_channelinfo: true
          can_messageinfo: true
          can_userinfo: true
          can_roleinfo: true
          can_emojiinfo: true
          can_snowflake: true
          can_nickname: true
          can_vcmove: true
          can_vckick: true
          can_help: true
          can_context: true
          can_jumbo: true
          can_avatar: true
          can_source: true
      - level: '>=100'
        config:
          can_reload_guild: true
          can_ping: true
          can_about: true

  #Logs
  logs:
    config:
    
      #channels:
        #'log channel id here': #log channel id here 
          #exclude: [] #exclude nothing, include everythinh

      format:
        timestamp: ""
        MEMBER_NOTE: "{timestamp} \U0001F58A Note added on {userMention(user)} by {userMention(mod)}"
        MEMBER_WARN: '{timestamp} ⚠️ {userMention(member)} was warned by {userMention(mod)}'
        MEMBER_MUTE: "{timestamp} \U0001F507 {userMention(user)} was muted indefinitely by {userMention(mod)}"
        MEMBER_TIMED_MUTE: "{timestamp} \U0001F507 {userMention(user)} was muted for **{time}** by {userMention(mod)}"
        MEMBER_UNMUTE: "{timestamp} \U0001F50A {userMention(user)} was unmuted by {userMention(mod)}"
        MEMBER_TIMED_UNMUTE: "{timestamp} \U0001F50A {userMention(user)} was scheduled to be unmuted in **{time}** by {userMention(mod)}"
        MEMBER_MUTE_EXPIRED: "{timestamp} \U0001F50A {userMention(member)}'s mute expired"
        MEMBER_KICK: "{timestamp} \U0001F462 {userMention(user)} was kicked by {userMention(mod)}"
        MEMBER_BAN: "{timestamp} \U0001F528 {userMention(user)} was banned by {userMention(mod)}"
        MEMBER_UNBAN: "{timestamp} \U0001F513 User (`{userId}`) was unbanned by {userMention(mod)}"
        MEMBER_FORCEBAN: "{timestamp} \U0001F528 User (`{userId}`) was forcebanned by {userMention(mod)}"
        MEMBER_SOFTBAN: "{timestamp} \U0001F528 {userMention(member)} was softbanned by {userMention(mod)}"
        MEMBER_JOIN: "{timestamp} \U0001F4E5 {new} {userMention(member)} joined (created {account_age} ago)"
        MEMBER_LEAVE: "{timestamp} \U0001F4E4 {userMention(member)} left the server"
        MEMBER_ROLE_ADD: "{timestamp} \U0001F511 {userMention(member)} received roles: **{roles}**"
        MEMBER_ROLE_REMOVE: "{timestamp} \U0001F511 {userMention(member)} lost roles: **{roles}**"
        MEMBER_ROLE_CHANGES: "{timestamp} \U0001F511 {userMention(member)} had role changes: received **{addedRoles}**, lost **{removedRoles}**"
        MEMBER_NICK_CHANGE: >-
          {timestamp} ✏ {userMention(member)}: nickname changed from **{oldNick}**
          to **{newNick}**
        MEMBER_USERNAME_CHANGE: >-
          {timestamp} ✏ {userMention(user)}: username changed from **{oldName}**
          to **{newName}**
        MEMBER_RESTORE: "{timestamp} \U0001F4BF Restored {restoredData} for {userMention(member)} on rejoin"
        MEMBER_TIMED_BAN: "{timestamp} \U0001F528 {userMention(user)} was tempbanned by {userMention(mod)} for {banTime}"
        MEMBER_TIMED_UNBAN: "{timestamp} \U0001F513 User (`{userId}`) was automatically unbanned by {userMention(mod)} after a tempban for {banTime}"
        CHANNEL_CREATE: "{timestamp} \U0001F58A Channel {channelMention(channel)} was created"
        CHANNEL_DELETE: "{timestamp} \U0001F5D1 Channel {channelMention(channel)} was deleted"
        CHANNEL_UPDATE: |-
          {timestamp} ✏ Channel {channelMention(newChannel)} was edited. Changes:
          {differenceString}
        THREAD_CREATE: "{timestamp} \U0001F58A Thread {channelMention(thread)} was created in channel <#{thread.parentId}>"
        THREAD_DELETE: "{timestamp} \U0001F5D1 Thread {channelMention(thread)} was deleted/archived from channel <#{thread.parentId}>"
        THREAD_UPDATE: |-
          {timestamp} ✏ Thread {channelMention(newThread)} was edited. Changes:
          {differenceString}
        ROLE_CREATE: "{timestamp} \U0001F58A Role **{role.name}** (`{role.id}`) was created"
        ROLE_DELETE: "{timestamp} \U0001F58A Role **{role.name}** (`{role.id}`) was deleted"
        ROLE_UPDATE: "{timestamp} \U0001F58A Role **{newRole.name}** (`{newRole.id}`) was edited. Changes:\n{differenceString}"
        MESSAGE_EDIT: >-
          {timestamp} ✏ {userMention(user)} edited their message (`{after.id}`) in
          {channelMention(channel)}:

          **Before:**{messageSummary(before)}**After:**{messageSummary(after)}
        MESSAGE_DELETE: "{timestamp} \U0001F5D1 Message (`{message.id}`) from {userMention(user)} deleted in {channelMention(channel)} (originally posted at **{messageDate}**):{messageSummary(message)}"
        MESSAGE_DELETE_BULK: "{timestamp} \U0001F5D1 **{count}** messages by {authorIds} deleted in {channelMention(channel)} ({archiveUrl})"
        MESSAGE_DELETE_BARE: "{timestamp} \U0001F5D1 Message (`{messageId}`) deleted in {channelMention(channel)} (no more info available)"
        MESSAGE_DELETE_AUTO: "{timestamp} \U0001F5D1 Auto-deleted message (`{message.id}`) from {userMention(user)} in {channelMention(channel)} (originally posted at **{messageDate}**):{messageSummary(message)}"
        VOICE_CHANNEL_JOIN: "{timestamp} \U0001F399 \U0001F535 {userMention(member)} joined {channelMention(channel)}"
        VOICE_CHANNEL_MOVE: "{timestamp} \U0001F399 ↔ {userMention(member)} moved from {channelMention(oldChannel)} to {channelMention(newChannel)}"
        VOICE_CHANNEL_LEAVE: "{timestamp} \U0001F399 \U0001F534 {userMention(member)} left {channelMention(channel)}"
        VOICE_CHANNEL_FORCE_MOVE: "{timestamp} \U0001F399 ✍ {userMention(member)} was moved from **{oldChannel.name}** to **{newChannel.name}** by {userMention(mod)}"
        VOICE_CHANNEL_FORCE_DISCONNECT: "{timestamp} \U0001F399 \U0001F6AB {userMention(member)} was forcefully disconnected from **{oldChannel.name}** by {userMention(mod)}"
        STAGE_INSTANCE_CREATE: "{timestamp} \U0001F4E3 Stage Instance `{stageInstance.topic}` was created in Stage Channel <#{stageChannel.id}>"
        STAGE_INSTANCE_DELETE: "{timestamp} \U0001F4E3 Stage Instance `{stageInstance.topic}` was deleted in Stage Channel <#{stageChannel.id}>"
        STAGE_INSTANCE_UPDATE: "{timestamp} \U0001F4E3 Stage Instance `{newStageInstance.topic}` was edited in Stage Channel <#{stageChannel.id}>. Changes:\n{differenceString}"
        EMOJI_CREATE: >-
          {timestamp} {emoji.mention} Emoji **{emoji.name}** (`{emoji.id}`) was
          created
        EMOJI_DELETE: "{timestamp} \U0001F44B Emoji **{emoji.name}** (`{emoji.id}`) was deleted"
        EMOJI_UPDATE: >-
          {timestamp} {newEmoji.mention} Emoji **{newEmoji.name}**
          (`{newEmoji.id}`) was updated. Changes:

          {differenceString}
        STICKER_CREATE: "{timestamp} \U0001F5BC️ Sticker `{sticker.name} ({sticker.id})` was created. Description: `{sticker.description}` Format: {emoji.format}"
        STICKER_DELETE: "{timestamp} \U0001F5BC️ Sticker `{sticker.name} ({sticker.id})` was deleted."
        STICKER_UPDATE: "{timestamp} \U0001F5BC️ Sticker `{newSticker.name} ({sticker.id})` was updated. Changes:\n{differenceString}"
        COMMAND: "{timestamp} \U0001F916 {userMention(member)} used command in {channelMention(channel)}:\n`{command}`"
        MESSAGE_SPAM_DETECTED: "{timestamp} \U0001F6D1 {userMention(member)} spam detected in {channelMention(channel)}: {description} (more than {limit} in {interval}s)\n{archiveUrl}"
        OTHER_SPAM_DETECTED: "{timestamp} \U0001F6D1 {userMention(member)} spam detected: {description} (more than {limit} in {interval}s)"
        CENSOR: "{timestamp} \U0001F6D1 Censored message (`{message.id}`) from {userMention(user)} in {channelMention(channel)}: {reason}:\n```{messageText}```"
        CLEAN: "{timestamp} \U0001F6BF {userMention(mod)} cleaned **{count}** message(s) in {channelMention(channel)}\n{archiveUrl}"
        CASE_CREATE: >-
          {timestamp} ✏ {userMention(mod)} manually created new **{caseType}**
          case (#{caseNum})
        CASE_DELETE: >-
          {timestamp} ✂️ **Case #{case.case_number}** was deleted by
          {userMention(mod)}
        MASSUNBAN: '{timestamp} ⚒ {userMention(mod)} mass-unbanned {count} users'
        MASSBAN: '{timestamp} ⚒ {userMention(mod)} massbanned {count} users'
        MASSMUTE: "{timestamp} \U0001F4E2\U0001F6AB {userMention(mod)} massmuted {count} users"
        MEMBER_JOIN_WITH_PRIOR_RECORDS: >-
          {timestamp} ⚠ {userMention(member)} joined with prior records. Recent
          cases:
 
          {recentCaseSummary}
        CASE_UPDATE: >-
          {timestamp} ✏ {userMention(mod)} updated case #{caseNumber} ({caseType})
          with note:

          ```{note}```
        MEMBER_MUTE_REJOIN: '{timestamp} ⚠ Reapplied active mute for {userMention(member)} on rejoin'
        SCHEDULED_MESSAGE: >-
          {timestamp} ⏰ {userMention(author)} scheduled a message to be posted to
          {channelMention(channel)} on {datetime}
        SCHEDULED_REPEATED_MESSAGE: >-
          {timestamp} ⏰ {userMention(author)} scheduled a message to be posted to
          {channelMention(channel)} on {datetime}, repeated {repeatDetails}
        REPEATED_MESSAGE: >-
          {timestamp} ⏰ {userMention(author)} scheduled a message to be posted to
          {channelMention(channel)} {repeatDetails}
        POSTED_SCHEDULED_MESSAGE: "{timestamp} \U0001F4E8 Posted scheduled message (`{messageId}`) to {channelMention(channel)} as scheduled by {userMention(author)}"
        BOT_ALERT: '{timestamp} ⚠ **BOT ALERT:** {tmplEval(body)}'
        DM_FAILED: "{timestamp} \U0001F6A7 Failed to send DM ({source}) to {userMention(user)}"
        AUTOMOD_ACTION: "{timestamp} \U0001F916 Automod rule **{rule}** triggered by {userMention(users)}\n{matchSummary}\nActions taken: **{actionsTaken}**"
        SET_ANTIRAID_USER: '{timestamp} ⚔ {userMention(user)} set anti-raid to **{level}**'
        SET_ANTIRAID_AUTO: '{timestamp} ⚔ Anti-raid automatically set to **{level}**'
        
      ping_user: false
      allow_user_mentions: false
      timestamp_format: '[<t:]X[>]'
      include_embed_timestamp: true

  #Mutes
  mutes:
    config:
      mute_role: 'mute role id here'
      move_to_voice_channel: null
      kick_from_voice_channel: false
      dm_on_mute: true
      dm_on_update: true
      message_on_mute: true
      message_on_update: true
      message_channel: null
      mute_message: 'You have been muted on {guildName} server | Reason given: **{reason}**. If you continue your behaviour you may get an permanent ban!'
      timed_mute_message: >-
        You have been muted on {guildName} server for {time} | Reason given:
        **{reason}**. If you continue your behaviour you may get an permanent ban!
      update_mute_message: 'Your mute on {guildName} server has been updated to {time}.'
      remove_roles_on_mute: false
      restore_roles_on_mute: false
      can_view_list: false
      can_cleanup: false
    overrides:
      - level: '>=50'
        config:
          can_view_list: true
      - level: '>=100'
        config:
          can_cleanup: true

  #Tags
  tags:
    config:
      delete_with_command: true
      user_tag_cooldown: null
      global_tag_cooldown: null
      user_cooldown: null
      allow_mentions: false
      global_cooldown: null
      auto_delete_command: false
      categories: {}
      can_create: false
      can_use: false
      can_list: false
    overrides:
      - level: '>=50'
        config:
          can_use: true
          can_create: true
          can_list: true

  #Automod
  automod:
    config:
      rules:

        #Filter
        badwords:
          enabled: true
          triggers:
          - match_words:
              words: ['fuck', 'sex', 'blowjob', 'pussy', 'fxck', 'shemale', 'sluts', 'motherfucker', 'porn', 'セックス', 'くそ', 'ポルノ', 'seks', 'lucah', 'persetan']
              case_sensitive: false
              only_full_words: true
          actions:
            clean: true
            reply:
              text: 
                content: "<@{user.id}> Please kindly watch your language and keep a good environment in the server! :3"
              auto_delete: 4s
            warn:
              reason: 'Swearing!'

        #Thread
        autothread:
          enabled: false
          allow_further_rules: true
          triggers:
          - any_message: {}
          actions:
            start_thread:
              auto_archive: 1d
              name: "{user.username} your disccusion chat!"
              private: false
              limit_per_channel: 20
            clean: false

        #Phisherman
        filter_scam_links:
          enabled: true
          triggers:
            - match_links:
                phisherman:
                  include_suspected: true # It's recommended to keep this enabled to catch new scam domains quickly
                  include_verified: true
          actions:
            log: true
            clean: true
            reply:
              text:
                content: "<@{user.id}> Scam links detected by Phisherman"
              auto_delete: 6s
            #kick:
              #reason: |-
                #Scam links detected by Phisherman

    #Overrides
    overrides:

    #AutoThreads Enabled for the below channel
    - channel: "channel-id here" #channel id where u want to create your thread!
      config:
        rules:
          autothread:
            enabled: true

    #Automods wont trigger for admin & mod
    - level: '>=50'
      config:
        rules:
          badwords:
            enabled: false
          #autothread:
            #enabled: false
          #filter_scam_links:
            #enabled: false

```
---

# Note:
I will update this guide as soon as posible if the bot gets any updates!!
For now this guide is up-to-date and works perfectly.

# Thank you!!
Thanks for reading and i hope this guide helps you abit if it does make sure star this repository. <3

> Make sure join JumanJi's Hub:

[![Join our Discord server!](https://invidget.switchblade.xyz/fjAhHH6CFh)](https://discord.gg/fjAhHH6CFh)

---
