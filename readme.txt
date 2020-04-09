Local build steps:
https://developers.mattermost.com/contribute/server/developer-setup/
https://developers.mattermost.com/contribute/webapp/developer-setup/

Channel related API: 
api4/channel.go

Roles we have changed in the live DB: 

-- channel_user

-- Before
--  read_channel add_reaction remove_reaction manage_public_channel_members upload_file get_public_link create_post use_slash_commands manage_public_channel_properties delete_public_channel manage_private_channel_properties manage_private_channel_members delete_private_channel delete_post edit_post

-- After 
--  read_channel add_reaction remove_reaction manage_public_channel_members upload_file get_public_link create_post use_slash_commands manage_public_channel_properties delete_public_channel delete_post edit_post



-- team_user

-- Before
--  list_team_channels join_public_channels read_public_channel view_team create_public_channel create_private_channel invite_user add_user_to_team

-- After
--  list_team_channels join_public_channels read_public_channel view_team invite_user add_user_to_team



select * 
  from Roles as r
 where r.Permissions like '%CHANNEL%';


