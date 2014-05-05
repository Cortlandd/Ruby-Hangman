### Simple Hangman Game that Demonstrates basic functions in ruby ###

# Initialize Parameters
alphabet = ["A", "B", "C", "D", "E", "F", "G", "H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T", "U", "V", "W", "X", "Y", "Z"]
lives = 7
turn = 0

# Load Potential Words
words_file = File.open('words.txt')
words = words_file.readlines
words.shuffle!

### BEGIN ###
# Select a Random Word
word = words[rand(words.length)].chars.to_a
puts "A word has been generated!\n\n"

# Fix to remove \n from the word
word.delete_at(word.length-1)

# Generate Copy to Keep Track of Progress
word_copy = word

# Loop until Win or Lose
until lives == 0 || word_copy == []

	# Generate Display
	puts "Word: "
	word.each do |x|
     if alphabet.include?(x) == true
       print "_ "
     else 
       print "#{x} "
     end
   end
   
   puts "\nLives Remaining: #{lives}\nLetters Remaining: "

	alphabet.each do |x|
		print "#{x} "
	end
	
	puts "\n\nMake a Guess: "
	guessed_letter = gets.chomp.upcase.strip
	
	# Check for User Errors
	until alphabet.include?(guessed_letter) == true
	   puts "You already guessed that! Try another letter.\n"
		guessed_letter = gets.chomp.upcase.strip
	end
	
	# System Response
	alphabet.delete(guessed_letter)
	if word.include?(guessed_letter) == true
		word_copy.delete(guessed_letter)
		puts "\nCorrect!\n"
	else
		puts "\nIncorrect\n"
		lives--
	end
end


	# Check Result
		if word_copy == []
			puts "Nice job, you won!\n"
		else
			puts "Better luck next time! The correct answer was #{word.to_s}\n" 
		end
	end
end
