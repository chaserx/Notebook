# helpers

    # https://gist.github.com/1156691
      def screen_shot_and_save_page
      require 'capybara/util/save_and_open_page'
      require 'launchy'
      path = "/#{Time.now.strftime('%Y-%m-%d-%H-%M-%S')}"
      Capybara.save_page body, "#{path}.html"
      path = Rails.root.join("#{Capybara.save_and_open_page_path}" "#{path}.png").to_s
      page.driver.render path
      Launchy.open path
    end