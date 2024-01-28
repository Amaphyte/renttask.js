class Movie {
    constructor(title, genre, releaseYear) {
      this.title = title;
      this.genre = genre;
      this.releaseYear = releaseYear;
    }
  }
  
  class MovieStore {
    constructor() {
      this.movies = [];
      this.rentedMovies = [];
    }
  
    addMovie(movie) {
      this.movies.push(movie);
    }
  
    rentMovie(title) {
      const movieIndex = this.movies.findIndex(movie => movie.title === title);
  
      if (movieIndex !== -1) {
        const rentedMovie = this.movies.splice(movieIndex, 1)[0];
        this.rentedMovies.push(rentedMovie);
        console.log(`${rentedMovie.title} has been rented.`);
      } else {
        console.log(`Movie not found: ${title}`);
      }
    }
  
    displayAvailableMovies() {
      console.log("Available Movies:");
      this.movies.forEach(movie => console.log(movie.title));
    }
  
    displayRentedMovies() {
      console.log("Rented Movies:");
      this.rentedMovies.forEach(movie => console.log(movie.title));
    }
  }
  
  // INSTANTIATION
  const movieStore = new MovieStore();
  
  const movie1 = new Movie("The sea monster", "Horror", 2010);
  const movie2 = new Movie("Love in a park", "Drama", 1994);
  const movie3 = new Movie("The lost child", "Drama", 2022);
  const movie4 = new Movie("Money Heist", "Drama", 2020);
  
  movieStore.addMovie(movie1);
  movieStore.addMovie(movie2);
  movieStore.addMovie(movie3);
  movieStore.addMovie(movie4);
  
  movieStore.displayAvailableMovies();
  
  movieStore.rentMovie("The sea monster");
  movieStore.displayAvailableMovies();
  movieStore.displayRentedMovies();
  
