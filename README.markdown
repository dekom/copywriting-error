# Error Reproduction #
1. Create refinerycms app
2. Install refinerycms-copywriting
3. Install refinerycms-page-images and check functional admin edit page
4. Remove refinerycms-page-images (with `rails d refinery:page_images` and
   remove gem dependency)
5. Visit admin edit page

# Error Message #
`NoMethodError in Refinery/admin/pages#edit`

`undefined method 'copywriting_phrases' for #<Refinery::Page:0x000000053a9738>`

Around line #1:
    1: <% copywriting_phrases = @page.copywriting_phrases %>
    2: <% if copywriting_phrases and copywriting_phrases.any? %>
    3:   <div class='wym_skin_refinery page_part' id='copywriting-tab'>
    4:     <ul>

`Trace of template inclusion:
~/.rvm/gems/ruby-1.9.3-p125@copywriting/gems/refinerycms-pages-2.0.3/app/views/refinery/admin/pages/_form_page_parts.html.erb,
~/.rvm/gems/ruby-1.9.3-p125@copywriting/gems/refinerycms-pages-2.0.3/app/views/refinery/admin/pages/_form.html.erb,
~/.rvm/gems/ruby-1.9.3-p125@copywriting/gems/refinerycms-pages-2.0.3/app/views/refinery/admin/pages/edit.html.erb`
