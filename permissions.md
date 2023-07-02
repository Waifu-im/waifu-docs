# Permissions

Some routes in our API require specific permissions to perform certain actions. When accessing user-specific resources or performing actions on your own account, your authentication token grants you full permissions. However, for certain actions that are not related to your account, you may need additional permissions.

## Available Permissions

<table><thead><tr><th width="202">Name</th><th>Description</th></tr></thead><tbody><tr><td>admin</td><td>This permission grants full administrative access to the API, allowing management of user accounts, images, and other resources. Only users with the "admin" permission can perform administrative actions.</td></tr><tr><td>view_favorites</td><td>This permission allows users to view their favorites.</td></tr><tr><td>manage_favorites</td><td>This permission allows users to add or remove images from their favorites.</td></tr><tr><td>report</td><td>Users with this permission can report inappropriate, offensive or wrongly labelled images in the API. This helps us maintain a safe and respectful environment for all users.</td></tr></tbody></table>
