# TelegramBot with Environment variable using Kubernetes

Para ejecutar la imagen del bot aplicando el deployment configurado en el archivo ejecutar el comando:

```plaintext
kubectl apply -f deployment.yaml
```

**Resultados** 

PS C:\docker\ejercicio_10\deployment> kubectl get all
pod/telegrambot-deployment-7f599444b4-xbmh5   1/1     Running   0          11s

NAME                 TYPE        CLUSTER-IP   EXTERNAL-IP   PORT(S)   AGE
service/kubernetes   ClusterIP   10.96.0.1    <none>        443/TCP   2d

NAME                                     READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/telegrambot-deployment   1/1     1            1           11s

NAME                                                DESIRED   CURRENT   READY   AGE
replicaset.apps/telegrambot-deployment-7f599444b4   1         1         1       11s

**Logs del Pod**

```plaintext
I, [2022-08-03T21:01:18.854428 #1]  INFO -- : Starting bot
I, [2022-08-03T21:02:36.444374 #1]  INFO -- : Incoming message: text="/version" uid=1005325235
D, [2022-08-03T21:02:36.444671 #1] DEBUG -- : From: @lugoea, message: #<Telegram::Bot::Types::Message:0x000055e33fe45ae8 @message_id=5, @from=#<Telegram::Bot::Types::User:0x000055e33fe2d038 @id=1005325235, @is_bot=false, @first_name="Edgar", @username="lugoea", @language_code="es", @last_name=nil>, @chat=#<Telegram::Bot::Types::Chat:0x000055e33fe2a270 @id=1005325235, @first_name="Edgar", @username="lugoea", @type="private", @title=nil, @last_name=nil, @all_members_are_administrators=nil, @photo=nil, @description=nil, @invite_link=nil, @pinned_message=nil>, @date=1659560556, @text="/version", @entities=[#<Telegram::Bot::Types::MessageEntity:0x000055e33fe1a910 @offset=0, @length=8, @type="bot_command", @url=nil, @user=nil>], @forward_from=nil, @forward_from_chat=nil, @forward_from_message_id=nil, @forward_signature=nil, @forward_sender_name=nil, @forward_date=nil, @reply_to_message=nil, @edit_date=nil, @media_group_id=nil, @author_signature=nil, @caption_entities=[], @audio=nil, @document=nil, @animation=nil, @game=nil, @photo=[], @sticker=nil, @video=nil, @voice=nil, @video_note=nil, @caption=nil, @contact=nil, @location=nil, @venue=nil, @poll=nil, @new_chat_members=[], @left_chat_member=nil, @new_chat_title=nil, @new_chat_photo=[], @delete_chat_photo=nil, @group_chat_created=nil, @supergroup_chat_created=nil, @channel_chat_created=nil, @migrate_to_chat_id=nil, @migrate_from_chat_id=nil, @pinned_message=nil, @invoice=nil, @successful_payment=nil, @connected_website=nil>
```
