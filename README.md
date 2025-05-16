# 🚀 Active Storage Dashboard

A beautiful Rails engine that provides a sleek, modern dashboard for monitoring and inspecting Active Storage data in your Rails application.

![Active Storage Dashboard Screenshot](https://github.com/giovapanasiti/active_storage_dashboard/blob/main/screenshots/dashboard.png)

*Note: Replace with your actual screenshot after deployment*

## ✨ Features

- 📊 Overview of Active Storage usage statistics
- 🔍 Browse and inspect blobs, attachments and variant records
- 📝 View metadata, file details, and relationships
- 🎨 Modern, responsive UI with animations
- 🚫 No external dependencies (vanilla JavaScript and CSS)

## 📥 Installation

Add this line to your application's Gemfile:

```ruby
gem 'active_storage_dashboard'
```

And then execute:

```bash
$ bundle
```

## 🔧 Usage

Mount the engine in your `config/routes.rb` file:

```ruby
Rails.application.routes.draw do
  # IMPORTANT: Make sure the mount path does not contain any special characters
  # Use a simple path like '/active-storage-dashboard' or '/storage-dashboard'
  # This is crucial for proper URL generation
  mount ActiveStorageDashboard::Engine, at: "/active-storage-dashboard"
end
```

Then visit `/active-storage-dashboard` in your browser to see the beautiful dashboard.

### 📁 File Downloads

The dashboard provides direct file download capabilities from both the list and detail views. Simply click on the download button to get your files.

### 📸 Screenshots

<details>
  <summary>Click to see more screenshots</summary>
  
  #### Dashboard Overview
  ![Dashboard Overview](https://github.com/giovapanasiti/active_storage_dashboard/blob/main/screenshots/dashboard.png)
  
  #### Blob Details
  ![Blob Details](https://github.com/giovapanasiti/active_storage_dashboard/blob/main/screenshots/blob-details.png)
  
  #### Files Gallery
  ![Files Gallery](https://github.com/giovapanasiti/active_storage_dashboard/blob/main/screenshots/files-gallery.png)
  
</details>

## 🔒 Security Considerations

This dashboard provides access to all Active Storage data. Consider adding authentication before using in production:

```ruby
# config/routes.rb
authenticate :user, -> (user) { user.admin? } do
  mount ActiveStorageDashboard::Engine, at: "/active-storage-dashboard"
end
```

or with devise:

```ruby
constraints lambda { |req| req.session[:user_id].present? || (req.env['warden'] && req.env['warden'].user(:user)) } do
  mount ActiveStorageDashboard::Engine, at: "/active-storage-dashboard"
end
```


## 🤝 Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/giovapanasiti/active-storage-dashboard.

## 📝 License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT). 