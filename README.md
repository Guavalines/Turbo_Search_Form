# TURBO SEARCH FORM

## Description
This is a real-time search form that allows users to search for bands.

## Highlights:
- Uses STIMULUS JS and TURBO FRAMES on the front end
- Includes TAILWIND

![Turbo Search](https://user-images.githubusercontent.com/100665876/213370341-cd8152a8-0cae-40d2-9ddc-555982881fc5.jpeg)

- Here is the bands controller index:

```
  def index
    if params[:query].present?
      @bands = Band.where("name LIKE ?", "#{params[:query]} %")
    else
      @bands = Band.all
    end

    if turbo_frame_request?
      render partial: "bands", locals: { bands: @bands }
    else
      render :index
    end
  end
 ```


## Please initialize the following before starting the app:

### Versions

![Ruby](https://img.shields.io/badge/Ruby-CC342D?style=for-the-badge&logo=ruby&logoColor=white) 3.0.3p157 (2021-11-24 revision 3fb7d2cadc) [x86_64-linux]

![Ruby on Rails](https://img.shields.io/badge/Ruby_on_Rails-CC0000?style=for-the-badge&logo=ruby-on-rails&logoColor=white) 7.0.4

![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)

### Setup

```
 git clone git@github.com:guavalines/Turbo_Search_Form.git
 cd rails-task-manager
 rails db:create db:migrate db:seed:replant
 bundle install
 yarn install
 rails server
```
Open your browser and visit localhost:3000
