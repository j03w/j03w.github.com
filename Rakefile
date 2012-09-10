task :build do
	system("jekyll")
end

task :post do
	throw "No title given" unless ARGV[1]
	title = ""
	ARGV[1..ARGV.length - 1].each { |v| title += " #{v}" }
	title.strip!
	id = Dir[File.join('_posts/','*.md')].count + 1
	now = Time.now
	path = "_posts/#{now.strftime('%F')}-#{title.downcase.gsub(/[\s\.]/, '-').gsub(/[^\w\d\-]/, '')}.md"

	File.open(path, "w") do |f|
		f.puts "---"
		f.puts "layout: post"
		f.puts "post_id: #{id}"
		f.puts "title: #{title}"
		f.puts "slug: #{title}"
		f.puts "date: #{now.strftime('%F %T %z')}"
		f.puts "description: "
		f.puts "---"
		f.puts ""
		f.puts ""
	end
	
	exit
end