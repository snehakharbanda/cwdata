#' Get crop yield
#'
#' This function gets crop yield.
#'
#' This function does get crop yield.
#'
#' @return
#' @examples
#' get_export_yield()
#' @export

get_crop_yield <- function (){

  entity <- code <- year <- crop <- NULL #to tell R i know what i am doing and silence the notes while checking
  `%>%` <- magrittr:: `%>%` #assign pipe operator to local object %>%

  url <- 'https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2020/2020-09-01/key_crop_yields.csv'

  readr::read_csv(url) %>%
    janitor::clean_names() %>%
    tidyr::pivot_longer(
      cols = -c(entity, code, year),
      names_to = "crop",
      values_to = "yield"
    ) %>%
    dplyr::mutate(crop = gsub("_tonnes_per_hectare", "", crop))

}
